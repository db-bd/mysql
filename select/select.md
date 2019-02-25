## Select Count(*) for Multiple Tables
```sql
SELECT
  (SELECT
     COUNT(0)
   FROM `udr`) AS `udr`,
  (SELECT
     COUNT(0)
   FROM `occurances`) AS `occur`,
  (SELECT
     COUNT(0)
   FROM `wallet`) AS `wallet`
```

## Create a View for Count(*)
```sql
DELIMITER $$

CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`%` SQL SECURITY DEFINER VIEW `total` AS 
SELECT
  (SELECT
     COUNT(0)
   FROM `udr_raw`) AS `udr`,
  (SELECT
     COUNT(0)
   FROM `occurances`) AS `occur`,
  (SELECT
     COUNT(0)
   FROM `data_wallet`) AS `data_wallet`$$
   
DELIMITER ;
```
