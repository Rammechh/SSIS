# SSIS
## Aggregation (Group by, count, count distinct)
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
       + In missing records all column with "Null" title failed. So, Title == "Mr." fails on Null.
       + NULL functions will help,Use REPLACENULL(Title,"Not Mr.") == "Mr." [If Mr then Mr==Mr pass, If Ms then Ms==Mr fail, if Null then Not Mr==Mr fail ]
---
## Row Sampling and Percentage Sampling
  + Under Other Transforms in Toolbox -> Row Sampling & Percentage Sampling
      + Row Sampling -> Randomly select some of the records and No.of.rows can be specified.
      * Selecting the '**Use the Following Random Seed**' option will fetch the same sample datas used for testing purposes
      * Will have two types of data 1) Sampling selected Output 2) Sampling Unselected Output
---
## Excel as Source
  + Select the Source as Excel and select the file path.
  + Select Table or View
  + Select Name of Excel sheet
---
## Flat File
  + Slect flat fle as source, select the file path, Select the Delimiter option and can select colon(:), Semicolon(;), Vertical bar(|), Comma(,), Tab(t), Carraige return(CR), Line feed(LF)
  + We can skip the rows, In Advanced tab can change Column name and data type.
  ### Excel as Destination
  * Select the Excel File as Destination
  * In Conn Manager, select the path and specify the name eg. Output1.xls and choose Microsoft Excel 97-2003.
  * double click excel and select new to create table pseudo sql code. Select Excel destination.
  * Right click on Excel, Advanced editor and select the correct data types in 'Input and output properties' tab. Compare Input and External columns.
  * Or else, use data conversion in middle.
---
## Union All
  + Used to Join datas from multiple source 
  + Add data conversion tabs to combine data
  + Use sort and derived columns to sort the data
---
## Merge
  + Merge Joins two or more sorted sources into single
  + Column data types must be converted and sorted to get complete required data
  + Added one package 'Practice'
---
## Auditing
  + Will be used to get real time data, 'Execution Start time', Machine name etc.
  + Options under Audit 1)Execution instance GUID(unique ID) 2)Package ID 3)Package Name 4)Version ID 5)Execution Start time 6)Machine name 7)Username 8)Taskname
  + Can also add derived columns after auditing and used for other functions like GETDATE etc.,
  + It can also be used to store audit datas in different table (good pracice for security)
  + Audit Package also attached.
---
## Adding Variables
  + At the top right corner, Can add the varibales
  + Variables uesd to store values. Eg: Row Count function will fetch the No.of.rows, it can be added to that variable
  + Can add break pts in Control flow
