# Databricks Lakeflow Pipeline Demo  
<img width="477" height="768" alt="image" src="https://github.com/user-attachments/assets/fed34ed8-ec01-49e9-95e8-dd3a1674c1fe" />


1. Select ETL Pipeline  
    <img width="1503" height="504" alt="image" src="https://github.com/user-attachments/assets/61e945e8-bec3-4843-b8f7-8f6b7d98fa1f" />


2 .  I am using default schema for this demo  <img width="1521" height="773" alt="image" src="https://github.com/user-attachments/assets/cdaec597-81c5-42ff-8d04-08c2280083c2" />

3.  It will create folder and generic file name for SQL file called "my_transformation.sql" . Rename it to "BronzetoGoldTransformation.sql"  
4.   <img width="1820" height="850" alt="image" src="https://github.com/user-attachments/assets/4160ea6e-5138-4df4-9844-03c53af45e98" />
   
5.   <img width="1574" height="931" alt="image" src="https://github.com/user-attachments/assets/87a66752-4433-4b18-967a-0b73310baca5" />

6. Below code snippet is added in sql file ( I will be provide github link )

7. <img width="1548" height="954" alt="image" src="https://github.com/user-attachments/assets/46e96508-00b8-4a3b-b9e0-418958a3352e" />

8. Just for awareness, I am using the sample delta table provided by Databricks in samples
9. <img width="440" height="852" alt="image" src="https://github.com/user-attachments/assets/9dfcb389-b558-48a5-a8f0-dd091ac87ce8" />
10. if you run below command, you will be able to see data in the trip table
11. <img width="1364" height="540" alt="image" src="https://github.com/user-attachments/assets/a421310c-bbd8-4d38-90d3-ed3e89abffaf" />

12. I ran pipeline <img width="1825" height="990" alt="image" src="https://github.com/user-attachments/assets/7a5d8560-890a-4053-a528-e237f984a820" />

13. <img width="1796" height="919" alt="image" src="https://github.com/user-attachments/assets/6efa7105-aa02-4512-ba7c-b32a53cddd75" />
14. <img width="1855" height="946" alt="image" src="https://github.com/user-attachments/assets/a5f2b1fc-ebfb-4e07-b17f-250b2efbeebb" />

15. Pipeline is successfully completed .. You can see results below
16.  <img width="1154" height="569" alt="image" src="https://github.com/user-attachments/assets/20a4bc79-8a98-4f78-9b09-f4210109381d" />
17.  <img width="1131" height="585" alt="image" src="https://github.com/user-attachments/assets/5ad46322-c121-415c-8e12-c553f98b4e6e" />
18.  <img width="1012" height="702" alt="image" src="https://github.com/user-attachments/assets/437955fe-c305-42c5-8138-b3610be60a9c" />

19.  I added another sql snippet to create materialized view to show it in powerbi CREATE OR REPLACE MATERIALIZED VIEW nytaxi_gold_view
AS
SELECT
  date_trunc('day', tpep_pickup_datetime) AS trip_date,
  AVG(trip_distance) AS avg_distance,
  SUM(fare_amount) AS total_revenue
FROM nytaxi_silver_updated
GROUP BY date_trunc('day', tpep_pickup_datetime);

20. After re-running pipeline, diagram generated like  below  <img width="770" height="350" alt="image" src="https://github.com/user-attachments/assets/048a75ef-e638-4e28-8db1-c73492d263d8" />
21. Materialized view also created   <img width="1012" height="682" alt="image" src="https://github.com/user-attachments/assets/818e07b6-40f0-4955-96db-d4de660933b7" />

22. All table we created are available in default schema
23. <img width="465" height="405" alt="image" src="https://github.com/user-attachments/assets/ee272901-3ba8-427c-bc69-38611d65adbc" />












