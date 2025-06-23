# 🐾 Zoo Shop Inventory & Sales Management System

This repository contains the database design and documentation for a real-world **Zoo Shop**, a retail business that sells both **pet-related products** and **live animals**. The database was created to handle everyday operations such as inventory tracking, customer transactions, and supplier management, while maintaining data integrity and supporting business scalability.

---

## 📘 Project Description

**The Zoo Shop** offers a wide range of products such as:
- Pet accessories (collars, cages)
- Pet food
- Toys
- Live animals (e.g., snakes, rabbits, fish)

To manage these operations, the store required a database solution that would:
- Keep detailed records of customer purchases
- Track inventory of both products and pets
- Maintain supplier information
- Distinguish between live pet sales and general merchandise
- Enable reporting on sales, stock levels, and supplier activity

The system design follows best practices in database normalization, ensures one-time sales of live pets, and is prepared for integration with applications or reporting tools.

---

## 🧱 Entity Overview

| Entity         | Purpose |
|----------------|---------|
| `Customer`     | Stores customer details including contact and registration data |
| `Product`      | Stores non-living items such as food, toys, and accessories |
| `Pet`          | Represents live animals sold individually with specific attributes |
| `Category`     | Defines product types (e.g., Food, Toys, Accessories) |
| `Supplier`     | Holds information about suppliers for both products and pets |
| `Sale`         | Captures individual transactions per customer |
| `Sale_product` | Records products sold in each sale with quantity and price |
| `Sale_pet`     | Tracks pet sales — each pet is sold only once |

---

## 🔗 Relationships & Constraints


- `Customer → Sale`: One customer can place many orders
- `Sale → Sale_product`: A sale can include many products
- `Sale → Sale_pet`: A sale can include pet(s)
- `Pet → Sale_pet`: **One-to-One** – each pet is sold once
- `Category → Product`: Products are grouped by category
- `Supplier → Product / Pet`: Suppliers provide goods or animals

The **Pet → Sale_pet** relationship is enforced as one-to-one using a `UNIQUE` constraint, as pets are living items and cannot be resold.

---

## 🧠 Normalization

This schema adheres to **Third Normal Form (3NF)**:
- ✅ 1NF: Atomic values and no repeating groups
- ✅ 2NF: Full functional dependency on primary keys
- ✅ 3NF: No transitive dependencies

---

## 🗺️ ER Diagram

You can view the full ER Diagram here:  
📎 [Lucidchart ERD](https://lucid.app/lucidchart/b969963d-2b7f-4d08-bb97-2bc27998fba2/edit?invitationId=inv_e3836027-6936-4156-ac94-494568839749&page=0_0)

---

## 📁 Project Files

| File | Description |
|------|-------------|
| `zoo_shop_schema.sql` | SQL script for table creation |
| `README.md`           | Project documentation |
| `ERD.png`             | Optional image export of the ER Diagram |
| `Adewole_Oyediran-DB_Zoo_Shop.docx` | Full design report |

---

## 🧑‍💻 Author

**Name**: Adewole Benjamin Oyediran  
**Project**: Zoo Shop Database  
**Email**: bensha2019@outlook.com

**LinkedIn**: https://www.linkedin.com/in/adewole-oyediran

---

## 📌 License

This project is intended for educational, academic, and prototyping purposes. For commercial use or adaptation, please contact the author.

