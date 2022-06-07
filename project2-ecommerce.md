- # Project 2: E-Commerce Database  
- # ER diagram  
	- Firstly, the ER diagram was created via https://online.visual-paradigm.com  
	- ![erd](https://user-images.githubusercontent.com/80232250/172428153-b4f423ba-c4c2-41fc-a933-ebac54708e1a.png)

---
- # CREATE TABLE  
	- Then, after completed the ER-Diagram, we could picture it into SQL.  
	- Open SQL, and start with creating tables.  
	- ## `PRIMARY KEY`  
		- ### `products`  
		  ```
		  			  CREATE TABLE product
		  			  (
		  			  	id	INTEGER,
		  			  	sku TEXT,
		  			  	name TEXT,
		  			  	price INTEGER,
		  			  	descriptions TEXT,
		  			  	weight INTEGER,
		  			  	image TEXT,
		  			  	category TEXT,
		  			  	date_created NUMERIC,
		  			  	stock INTEGER,
		  			  	PRIMARY KEY(id)
		  			  )
		  			  
		  ```
		- ### `options`  
		  ```
		  			  CREATE TABLE options
		  			  (
		  			  	id	INTEGER,
		  			  	option_name TEXT,
		  			  	PRIMARY KEY(id) 
		  			  )
		  			  
		  ```
		- ### `categories`  
		  ```
		  			  CREATE TABLE categories
		  			  (
		  			  	id	INTEGER,
		  			  	name TEXT,
		  			  	description TEXT
		  			  	thumbnail TEXT
		  			  	
		  			  	PRIMARY KEY(id) 
		  			  )
		  			  
		  ```
		- ### `customers`  
		  ```
		  			  CREATE TABLE categories
		  			  (
		  			  	id	INTEGER,
		  			  	email TEXT,
		  			  	password TEXT,
		  			  	full_name TEXT,
		  			  	billing_address TEXT,
		  			  	default_shipping_address TEXT,
		  			  	phone NUMERIC,
		  			  	
		  			  	PRIMARY KEY(id) 
		  			  )
		  			  
		  ```
		-  
---
## `FOREIGN KEY`  
- ### `product_options`  
		  ```
		  			  CREATE TABLE product_options
		  			  (
		  			  	id	INTEGER,
		  			  	option_id INTEGER,
		  			  	product_id INTEGER,
		  			  	
		  			  	FOREIGN KEY(option_id) REFERENCES options(id)
		  			  	FOREIGN KEY(product_id) REFERENCES products(id)
		  			  )
		  			  
		  			  
		  ```
- ### `product_categories`  
		  ```
		  			  CREATE TABLE product_categories
		  			  (
		  			  	id	INTEGER,
		  			  	category_id INTEGER,
		  			  	product_id INTEGER,
		  			  	
		  			  	FOREIGN KEY(category_id) REFERENCES categories(id)
		  			  	FOREIGN KEY(product_id) REFERENCES products(id)
		  			  )
		  			  
		  ```
	-  
- ### `orders`  
		  ```
		  			  CREATE TABLE orders
		  			  (
		  			  	id	INTEGER,
		  			  	customer_id INTEGER,
		  			  	amount INTEGER,
		  			  	shipping address TEXT,
		  			  	order_address TEXT,
		  			  	order_email TEXT,
		  			  	order_date NUMERIC,
		  			  	order_status TEXT,
		  			  	
		  			  	FOREIGN KEY(customer_id) REFERENCES customers(id) 
		  			  )
		  ```
- ### `order_details`  
		  ```
		  			  CREATE TABLE orders_details
		  			  (
		  			  	id	INTEGER,
		  			  	order_id INTEGER,
		  			  	product_id INTEGER,
		  			  	price INTEGER,
		  			  	sku TEXT,
		  			  	quantity INTEGER,
		  			  	
		  			  	FOREIGN KEY(order_id) REFERENCES orders(id),
		  			  	FOREIGN KEY(product_id) REFERENCES products(id)
		  			  )
		  ```
-  
- # Database Structure  
	- After completed creating the tables, we could see the data structures.  
	-  ![datastructure](https://user-images.githubusercontent.com/80232250/172428228-073423a8-9e4b-47a1-a8b2-4e5ee4e96801.png)

	-  
-  
