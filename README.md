# 🍽️ Recipe Management System (SQL Project)

This project implements a fully relational database system for managing recipes, ingredients, users, comments, and ratings using SQL. It supports complex query operations, data validation through stored procedures and triggers, and can be integrated with a web-based frontend.

## 🚀 Features

- **Database schema** for users, recipes, categories, ingredients, ratings, and comments.
- **Up and down scripting** for database creation and cleanup.
- **Stored procedures** for secure rating management.
- **Triggers** for enforcing data integrity (e.g., difficulty level validation).
- **Sample data population** for quick testing.
- **Advanced SQL queries** to extract meaningful insights (e.g., top-rated recipes, recipes with fewer ingredients, user activity).

## 🛠️ Technologies Used

- SQL (MS SQL Server / T-SQL)
- Relational database modeling (ERD, Logical/Conceptual Design)
- Stored Procedures & Triggers
- Joins, Aggregations, Subqueries

## 📂 File Structure

- `recipe-management-final-code.sql`: Contains full database creation script including:
  - Table creation
  - Foreign key relationships
  - Data inserts
  - Stored procedure for adding/updating ratings
  - Trigger to enforce difficulty level constraints
  - Sample queries

## 📊 Example Use Cases

- Retrieve recipes with fewer than 3 ingredients
- Identify top-rated recipes by category
- Get users who have rated and commented
- Find the recipe with the shortest preparation time
- Enforce difficulty level constraints with a trigger
- Add/update ratings using a stored procedure

## 🧠 Sample Query

```sql
-- Retrieve top-rated dessert recipes
SELECT c.category_name, r.recipe_title, AVG(rt.rating_score) AS average_rating
FROM recipes r
JOIN ratings rt ON r.recipe_id = rt.rating_recipe_id
JOIN categories c ON r.recipe_category_id = c.category_id
WHERE c.category_name = 'Dessert'
GROUP BY c.category_name, r.recipe_title
ORDER BY average_rating DESC;
