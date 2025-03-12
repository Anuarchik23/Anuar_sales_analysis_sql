# Anuar_sales_analysis_sql
sales_analysis_sql

---

### 📌 **Файл `queries.sql` (SQL-запросы)**
В этом файле размести все SQL-запросы, чтобы их можно было легко скопировать и протестировать.

```sql
-- Создание таблицы продаж
CREATE TABLE Sales (
    sale_id SERIAL PRIMARY KEY,
    product_id INT,
    customer_id INT,
    quantity INT,
    price DECIMAL,
    sale_date DATE
);

-- Анализ продаж по месяцам
SELECT 
    EXTRACT(YEAR FROM sale_date) AS year,
    EXTRACT(MONTH FROM sale_date) AS month,
    SUM(quantity * price) AS total_sales
FROM Sales
GROUP BY year, month
ORDER BY year, month;
