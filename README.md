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
  + Source --> Multicast -> Destination1, D2, D3... (Saves memory and time instead of two source)
