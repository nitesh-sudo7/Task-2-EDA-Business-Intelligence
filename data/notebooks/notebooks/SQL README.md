-- Task 2: SQL Business Intelligence Queries

-- 1. Top 5 products by total revenue
SELECT product,
       SUM(revenue) AS total_revenue
FROM sales
GROUP BY product
ORDER BY total_revenue DESC
LIMIT 5;

-- 2. Monthly revenue trend
SELECT 
    MONTH(order_date) AS month,
    SUM(revenue) AS monthly_revenue
FROM sales
GROUP BY MONTH(order_date)
ORDER BY month;

-- 3. Revenue contribution by region
SELECT region,
       SUM(revenue) AS region_revenue
FROM sales
GROUP BY region
ORDER BY region_revenue DESC;

-- 4. Average order value
SELECT AVG(revenue) AS average_order_value
FROM sales;

-- 5. Customer segment performance
SELECT customer_segment,
       SUM(revenue) AS segment_revenue
FROM sales
GROUP BY customer_segment
ORDER BY segment_revenue DESC;

