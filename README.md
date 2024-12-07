# Food e-commerce
food e-commerce websites that have different pages for different roles such as ADMIN, USER, GUEST

## Data

* Products

| product_id | name | price | category |
|------------|------|-------|--------- |
| INT PRIMARY | VARCHAR | INT | ENUM('FOOD','DRINK','DESSERT') |

* Users

| user_id | user_name | password | role |
|---------|-----------|----------|------|
| VARCHAR PRIMARY KEY | VARCHAR | VARCHAR | ENUM('ADMIN','USER') |

* Notes

| date | user_id | order_id |
|------|---------|----------|
| DATETIME DEFAULT ON UPDATE | VARCHAR | INT FOREIGN KEY |

## Features
1. Admin
Can access dashboard which is :
* Can do CRUD for products
* Can delete user with role USER
* Can manage note

2. User
* Select some products and place the order with format :
```
{
  "order": [
    {
      "name": string,
      "price": number,
      "amount": number
    }
  ],
  "totalPrice": number
}
```
* readonly note

3. Guest
* Only read menu and will be ask to sign in/up if selecting any menus
