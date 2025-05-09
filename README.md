![Image](https://github.com/user-attachments/assets/3fa78bc7-a41f-4e8a-9412-cd61e1cff154)

# 🎵 SQL Data Analysis: Music Store Database

This project showcases a series of SQL queries and data exploration tasks on a fictional music store database using **PostgreSQL**. The analysis is focused on answering key business questions related to employees, customers, invoices, genres, and purchase behavior.

---

## 🧾 Objectives

- Identify top-performing employees and customers
- Analyze revenue trends by city and country
- Explore genre-based user preferences
- Perform customer segmentation based on purchases

---

## 🛠️ Technologies Used

- **PostgreSQL**
- **SQL**
- **pgAdmin** 

---

## 📌 Key Analytical Questions Covered

1. Who is the **senior-most employee** based on job title?
2. Which **countries** have the most invoices?
3. What are the **top 3 invoice totals** recorded?
4. Which **city generates the most revenue**? *(Ideal for targeting promotions)*
5. Who is the **best customer** in terms of total spending?
6. Identify all **Rock music listeners**, sorted by email.
7. Which **tracks have the highest unit price**?
8. Analyze **sales agents and their performance**.
9. Understand customer preferences by **genre** and **purchase count**.
10. Find customers who made **most purchases in top genres**.

---

## 📈 Sample Query (Best Customer)

```sql
SELECT customer.customer_id, first_name, last_name, SUM(invoice.total) AS total_spent
FROM customer
JOIN invoice ON customer.customer_id = invoice.customer_id
GROUP BY customer.customer_id
ORDER BY total_spent DESC
LIMIT 1;
