# CDC_Real_Time_Aggregation_in_Snowflake_Dynamic_Table
Developed a CDC (Change Data Capture) pipeline to aggregate the data in real-time using Snowflake Dynamic Table

Tech Stack:
1. Python script : To generate mock data in raw snowflake table
2. Snowflake Dynamic Table : To create bronze layer data, silver layer data after transformation and data validation, gold layer data with aggregation, Schedule task to run refresh command on gold layer table

**Steps to create pipeline:**
1. Open snowflake worksheet -> write and execute the sql commands given in(snowflake_dynamic table input files)
2. Open mock_cdc_data.py -> update the username, password & account
3. In cmd run the command -> pip install snowflake-connector-python
4. run the python script
5. In worksheet -> run select command on raw_data -> records will be displayed
6. Their will be no records in dynamic table because we need to refresh it
7. Run the refresh command on dynamic table.
8. Now try the select command we can see the records in dynamic table.
9. Execute the create task command (after task gets created by default it will be in suspended state so we need to resume it )
10. Now run the last select command which will trigger the task every 2 min,so integration will be done every 2 min.
11. We can check derived table by runing select command and the aggregated table with the same also.
    
