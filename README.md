# sqlGradebook
a SQL-based gradebook system that allows professors to  track grades for their students.

Instructions for using the SQL gradebook
A. setting up the database.
These steps will only need to be done the first time the program is used.
1. Install my SQL server if you don't already have it.
2. Open the command prompt.
3. Navigate to the directory to which you have unzipped the zip file.
4. Start the my SQL server (mysqld.exe)
5. Log on to the my SQL client as root.
6. create the database by using the following command: create database gradebook;
7. switch to the database by using the command: use gradebook;. This will allow the tables to be created in the correct place.
8. Run the following command: source sqlGradebook.sql. This will run the queries necessary to initialize the tables, procedures, and functions.
9. If any user other than root wishes to use the program:
a. to create a new user, run create user "<username>"@"localhost" identified by "<password>"; (replace <username> and <password> by the user's username and password).
b. If the user already exists, run grant all on gradebook.* to "<username">@"localhost" (replace <username> with the user's username). This will ensure that all necessary permissions are in place for the new user to successfully use the program.
c. In order for the new user to run the stored procedures, run grant select on mysql.proc to "<username>"@"localhost".
b. Running the program
With the my SQL server (mysqld.exe) running, run the command java -cp <classpath> SQLGradebook. <classpath> is the list of directories in which the java virtual machine will search for classes. For this program, the classpath should include the directory in which the SQLGradebook file is located and the path to the JDBC driver jar file (included). To include multiple directories in the classpath, separate the directories with semicolon. To include the current directory in the classpath, use . as the directory name. To include a jar file as part of the classpath, the jar extension must be included. For example, to include the xyz.jar file on the e drive, the appropriate item to include in the classpath would be "e:\xyz.jar". Some characters in a directory or jar file name may need to be quoted or escaped to ensure that the command prompt interprets them properly. If the program starts successfully, it will ask for your username and password; a successfull login will cause the program to enter a loop in which it prompts for and performs the actions specified in the design document. A failed login will cause the program to display an error message and exit.
