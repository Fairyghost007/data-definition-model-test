# data-definition-model-test

## 1. Create Tables with Constraints

```sql
CREATE TABLE Customer (
    Customer_id VARCHAR2(20) PRIMARY KEY,
    Customer_Name VARCHAR2(20) NOT NULL,
    Customer_Tel NUMBER
);

CREATE TABLE Product (
    Product_id VARCHAR2(20) PRIMARY KEY,
    Product_name VARCHAR2(20) NOT NULL,
    Price NUMBER CHECK (Price > 0)
);

CREATE TABLE Orders (
    Customer_id VARCHAR2(20),
    Product_id VARCHAR2(20),
    Quantity NUMBER,
    Total_amount NUMBER,
    FOREIGN KEY (Customer_id) REFERENCES Customer(Customer_id),
    FOREIGN KEY (Product_id) REFERENCES Product(Product_id)
);
```
## 2. Alter Tables to Add Columns
```sql
ALTER TABLE Product ADD Category VARCHAR2(20);

ALTER TABLE Orders ADD OrderDate DATE DEFAULT SYSDATE;
```

<img width="583" alt="Screen Shot 2024-11-18 at 19 43 54" src="https://github.com/user-attachments/assets/a7efb53f-5e4a-4482-b6eb-214466f6bc79">
<img width="463" alt="Screen Shot 2024-11-18 at 19 44 03" src="https://github.com/user-attachments/assets/b943503f-9bba-453b-8a70-ab1181478a79">


