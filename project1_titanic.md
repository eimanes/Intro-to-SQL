# SQL: Project 1
#####  by Eiman Salleh (SE May)
------------------------------

## Contents of the dataset [passengers.db]
  - The data shows the passengers aboard the Titanic (once was the largest ship in the world), and who survived from the sinking of the ship.
  - The dataset contains attributes on the passengers including age, sex, and socio-economic status.
  - There were few lifeboats in the Titanic ship to account for all of its passengers, and many of them did not survive.
  - This issue had led to new laws and regulations regarding the number of lifeboats required in each ship.
  - By evaluating this data, we may learn how each passenger's personal characteristics influenced their chances of survival, as well as if any particular grouping of passengers had priority for lifeboats.

## Displaying the table
  ```
  SELECT * FROM passengers
  ```
  ![image](https://user-images.githubusercontent.com/80232250/170904695-fd30583f-a9d5-43b0-a783-53f46626b72f.png)
  
## Exploratory analysis

### 1. What is the total number of individuals on the ship? `COUNT(column)`
```
SELECT COUNT(PassengerId) as Total_Passengers FROM passengers;
```
![image](https://user-images.githubusercontent.com/80232250/170905052-1403498e-0e6c-4b14-8ec2-756a3ff9dd8c.png)

### 2. What was the survival rate overall? `SUM(column)/total_passengers`
```
SELECT SUM(survived)/891.0 as Rate_Survived FROM passengers
```
![image](https://user-images.githubusercontent.com/80232250/170905355-3705478e-9057-4b75-97a7-b22781f27bb2.png)
- the integer of total number of passengers should be in float because we want the result in float.
- 40% of the Titanic's passengers who survived during the sinking.

#### 2.1 How many died? `where survived = integer`
```
SELECT COUNT(*) as Died
from passengers
where Survived = 0
```
![image](https://user-images.githubusercontent.com/80232250/170906621-ac8dc922-4cfe-4a26-8cf1-ff342637b427.png)

#### 2.2 How many survied?
```
SELECT COUNT(*) as survived
from passengers
where Survived = 1
```
![image](https://user-images.githubusercontent.com/80232250/170906651-0890eac9-187e-4cde-a040-95025fcb865e.png)


### 3. How many survived based on sex? `survived = integer AND sex = string`
#### 3.1 Men?
```
SELECT COUNT(*) as survived_male
from passengers
where Survived = 1 and Sex = 'male'
```
![image](https://user-images.githubusercontent.com/80232250/170906856-96ee301f-2cdf-4241-8be5-e5b398a8c9fa.png)

#### 3.2 Women? 
```
SELECT COUNT(*) as survived_female
from passengers
where Survived = 1 and Sex = 'female
```
![image](https://user-images.githubusercontent.com/80232250/170906900-7527f553-7149-4e34-9cbc-e557e0bef3e5.png)

### 4. What is the average of all passengers and of the survivors?
#### 4.1 Avg all passengers `AVG(column)`:
```
SELECT AVG(age) from passengers
```
![image](https://user-images.githubusercontent.com/80232250/170907207-aa94ef46-f0fd-44f2-94dc-e5aa7588fabf.png)

#### 4.2 Avg all survivors 
```
SELECT AVG(age) from passengers
WHERE survived = 1
```
![image](https://user-images.githubusercontent.com/80232250/170907618-f9b2cf17-18f5-4e1c-8a85-6fe00a84d354.png)

### 5. What is the survival rate by Passenger Class? `GROUP By`
```
SELECT Pclass, SUM(survived) as Survivors, COUNT(PassengerId) as Class_Passengers,
	(SUM(Survived)/count(PassengerId)) as Survival_Rate
FROM passengers
GROUP by Pclass
```
![image](https://user-images.githubusercontent.com/80232250/170908075-316aa63a-9996-4336-9468-084a4fa8bcf2.png)

### 6. How many Parents and Child survived?
```
SELECT count(Parch) from passengers
WHERE Parch > 0 AND Survived = 1
```
![image](https://user-images.githubusercontent.com/80232250/170908474-381172c8-93cf-4b46-adac-c03dbe230929.png)

