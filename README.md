# SSIS
## Aggregation
  + Aggregate data with fn's like Average, Sum, Count, Max & Min.
  + Choose OLE DB Source as Customer table
  + Aggregate fn in middle (select any one column(salesperson) and use group by operation, then select (* ) count all operation) 
  + Choose OLE DB Destination as Output03 table 
  + Now output will be same as [select salesperson, count(* ) from customer group by salesperson]
---
## MultiCast
  + Multicast Transformation in SSIS sends input data to multiple destination paths without applying any conditions or transformations. OR, Takes ONE Input and makes the logical COPY of data and passes the same data to multiple outputs.
  + Flow: Source --> Multicast -> Destination1, D2, D3... (Saves memory and time instead of two source)
---
## Conditional split
  + The Conditional Split Transformation task checks for the specified condition. It moves the data to an appropriate destination depending upon the condition.
  + Flow: Source-> Conditional split-> D1, D2
  + If Condition used in D1, D2 will pick the remaining records
  + In Cond. Split -> after dob. click drag and drop column and give condition Title == "Mr.", now run will throw Error, will be covered as Error Handling
      ### Error Handling
       + If any fails during run, goto Configure Error Output and select <b>"Ignore Failure"</b> in error and Truncation. Now run to get output
       + To get the records that are missing add "Derived column" to D1, D2. Which gives the missing records in truncation ("Redirect row")
