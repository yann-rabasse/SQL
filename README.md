# SQL
SQL practice queries



SELECT
  id
  , name as first_name
  , surname
  , creation_date
  , number_of_orders
  , total_turnover
  , case 
    WHEN number_of_orders >0 THEN 1
      ELSE 0
    END AS is_customers
  , CASE 
    WHEN number_of_orders=0 THEN "New"
    WHEN number_of_orders >= 1 AND number_of_orders <= 2 THEN "New"
    ELSE "Frequent"
    END AS segment
  , CASE
    WHEN number_of_orders = 0 THEN 0
    ELSE (total_turnover / number_of_orders) 
  END AS average_basket 
FROM `crucial-binder-437910-a7.Course14.gwz_customers` 
WHERE name IN ("Paul","George")
ORDER BY id
