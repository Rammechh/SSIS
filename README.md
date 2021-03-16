# SSIS
## Aggregation
  + Aggregate data with fn's like Average, Sum, Count, Max & Min.
  + Choose OLE DB Source as Customer table
  + Aggregate fn in middle (select any one column(salesperson) and use group by operation, then select (* ) count all operation) 
  + Choose OLE DB Destination as Output03 table 
  + Now output will be same as [select salesperson, count(* ) from customer group by salesperson]
