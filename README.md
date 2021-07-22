# FinancialTransactionRecordsAnalyser

A simple financial analyser that will read a correctly formatted and ordered csv which contains financial transactions, and will calculate the relative balance for an account during a specified time period. An example csv has been included. 

## Assumptions
Input file and records are all in a valid format 

Transaction are recorded in order 

Any account ID entered will exist in the record

That you have knowledge of Java and can use an IDE


## System Design
The main class, SystemInitalizer, contains a main method, transactionRecord function, and relativeAccountBalance function. The main method is responsible for the file path input, account number specified, and the start and end dates needed to perform the relative account balance calculation. 

TransactionRecord function will take a file path, and use a scanner to read each line of a csv. Each line is broken up into parts based on ",", each individual string is converted to their correct data type, and then stored in an ArrayList. Each array is then stored in another array, basically converting the csv into a nested array, keeping each line individual and easily accessed. 

relativeAccountBalance will take the nested array, as well as the accountID, start date and end date needed to calculated the relative account balance. A sum and a number of transaction variable is initialised first, then code will loop through the nested array, and check if any date is within the time period specified. If so, it will then check if the accountID matches anything within the records. If it does, the amount shown in the transaction is added or subtracted from the sum, depending on if the transaction type is "PAYMENT" or "REVERSAL". 
The number of transactions is incremented each time a relevant transaction occurs for the account. 
At the end, these numbers are returned to main, where they are printed to the console. 




## How to download/run code
I reccomend using an IDE to run this code. My preference for this was Netbeans.  
Start a new project, copy and paste the SystemAnalser.java file under the SourcePackage/<default package>, and make sure to edit your project prefence to use SystemAnalser as the main class. To run this class, click on the run button or green triangle (changes based on your IDE).

To run the test:
Select SystemAnalser.java, go to tools and click "Create/Update Tests". and create a new test file. Open SystemInitalizerTest, and copy and paste the testing code into your new testing file.
To run the unit test, right click on the SystemAnalser.java file and select "test file". This will run the unit tests. 

This code uses an example csv already stored in the project. In the class InitalizeSystem, under main, you can change what file you wish to load by changing the String filepath = "FinancialRecords.csv" -> to whatever file path you need.






## System coded on:
Product Version: Apache NetBeans IDE 12.2 /n
Java: 15.0.2;
Runtime: Java(TM) SE Runtime Environment 15.0.2+7-27
System: Mac OS X version 10.15.7 running on x86_64; UTF-8; en_AU (nb)

