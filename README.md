Download Link: https://assignmentchef.com/product/solved-cis336-lab-3-building-the-physical
<br>
<header class="entry-header">

 <p class="entry-title">The lab for this week addresses taking a logical database design (data model) and transforming it into a

</header>

5/5 - (3 votes)

physical model (tables, constraints, and relationships). As part of the lab, you will need to download the zip file titled CIS336Lab3Files from Doc Sharing. This zip file contains the ERD, Data Dictionary, and test data for the tables you create as you complete this exercise.

Your job will be to use the ERD Diagram found below as a guide to define the table structures and constraints using both CREATE TABLE and ALTER TABLE statements. Once this has been done, you will need to write the INSERT INTO TABLE statements to insert the data provided into the table. The data should verify that the constraints you have created are valid and define the correct referential and data integrity constraints asked for. Lastly, you will write SELECT statements to query the tables and verify the data was populated. Please use exactly the data provided, without addition, deletion, or alteration except as directed, as your results may be evaluated against expected results generated using this exact data set.

<strong>Narrative/Case Study</strong>

For this lab, you will be creating SQL statements to build a series of relational tables, using SQL CREATE statements in a script file format for the Student Database. You will then populate those tables through the use of INSERT statements with sample data.

You will need to create a script file and name it YourName_Lab3.txt containing the following code.

<ol type="1">

 <li>The drop table statements listed later in the specifications of this lab.</li>

 <li>The CREATE TABLE statements required to build the six tables.</li>

 <li>The INSERT statements necessary to insert all of the sample data.</li>

 <li>Six select statements to verify that the data is in the tables and accessible.</li>

</ol>

To help you accomplish this task successfully, you are being supplied with the ERD Diagram which follows, and the exact data to be inserted into each table, which may be found via the Doc Sharing tab on the course website.

The following guidelines are being provided to help assist you in creating your script file. Use the names for the tables and columns as listed in the ERD. Do not change them as it will affect your grade.

Creating Constraints

<ol>

 <li>Create all NOT NULL constraints as indicated in the ERD.</li>

 <li>Create all PK constraints as indicated in the ERD.</li>

 <li>Create all FK constraints as indicated in the ERD.</li>

</ol>

Create all of the tables and all of the constraints before populating any of the tables with data. Because FK constraints will be in place when the insert statements are executed, you will need to consider carefully which tables must be created before others in order to ensure that FK constraints are not violated.

The COURSE table has a self-referencing FK constraint. Specifically, some courses have prerequisite courses. Consequently, the record for a course possessing a prerequisite course cannot be successfully inserted into the table unless the record for the prerequisite course has already been inserted. This may require you to reorder the insert statements to resolve FK violations when loading the table. You may reorder the data provided for this table, but do not alter it.

The data for one table intentionally contains a record containing an FK constraint that is not resolved by a record in the parent table. This orphaned record has been included as an exercise for you to find. Because this record has an unreconciled FK constraint, it cannot be successfully inserted. You will need to delete or comment out the insert statement for this one record in order to produce a script that runs without errors.

Aside from reordering the data for the COURSE table as necessary, and commenting out/deleting the ONE record whose FK dependency cannot be resolved by the data provided, you are NOT to modify, add to, or delete from the data provided. Your SQL script must produce tables containing data identical to the expected solution set, or points will be deducted.

ALL character strings must be enclosed in single quotes. This includes alpha strings and alphanumeric (remember that any formatting within a numeric string makes it alphanumeric). If you are inserting a NULL, do not enclose the word NULL in single quotes, as this will insert the word NULL into the row. To insert a null you simply use the word NULL.

<strong>Deliverables</strong>

The deliverable for this lab will include the following documents.

<ol type="1">

 <li>Your script file. Create this file in Notepad, or another PURE TEXT editor—NOT Word. Make sure your name is in a comment area at the top of the script file. Use a double dash to create a one line comment.</li>

 <li>Your script file must execute without error. It is recommended that you begin early in the week, and post any questions to the Q &amp; A discussion in order to produce a working script by the due date. Be sure your name is on all documents and that all documents have been included in a single zip file for this week’s assignments. Refer to the following ERD in constructing your solution.StudentPKStudent_IDSalutationFirst_NameLast_NameStreet_AddressPhoneEmployerRegistration_DateFK1ZipEnrollmentPK,FK1Section_IDPK,FK2Student_IDEnroll_DateFinal_Grade</li>

</ol>

<strong>iLAB STEPS</strong>

<strong>STEP 1:</strong> The DROP StatementsA DROP TABLE statement must appear in your script file, prior to the SQL statements for creating the table in question. This will allow you to run and re-run your script file as often as you need to. Thevery first time you run your script the table does not exist, so the IF EXISTS clause causes the statement to be ignored. Thereafter, the table will be deleted, ensuring that your CREATE TABLE statement creates the table fresh and clean, with only the attributes present in the current revision of the CREATEstatement. Here is an example of one of the six DROP TABLE statements you will need to create.

<strong>STEP 2:</strong> The CREATE TABLE StatementsNext, define the CREATE TABLE statements for the six tables that you are to create based upon the ERD (provided above) for this lab. Be sure to follow the guidelines given above on how and where to create the different types of constraints for each table. This will include PK, FK, and NOT NULL constraints.

<strong>STEP 3:</strong> The INSERT Statements for the DataThe third step is to create the insert statements to insert the sample data into the tables created inStep 2. The data for each table is contained in text files, named for the table whose data it contains.Modify the format of the data (e.g., date formats and add or eliminate quote marks) as needed to craftyour insert statements, but do not change the inherent value of the data.

<strong>STEP 4:</strong> The SELECT StatementsThe next step of the lab will be to create the select statements to verify the data was inserted correctly. You should have six select statements; one for each table. The command is SELECT * FROM Table_Name;For example, to select all columns from the Student table, the command would be SELECT * FROM student;Be sure to save all of the above statements in your script file.

<strong>STEP 5:</strong> Testing and Verifying Your ScriptNow we come to the point of verifying that your script file works by creating all of the tables andinserting and selecting all of the data. Your script should execute without errors, and select the entirecontents of each table in turn. Inspect your query results to ensure that each column and row from each of the tables is as expected. Correct and repeat testing of your script until no errors occur, and theresults match expectations. You may also use the DESCRIBE command to display the table structure of each table, and verify that PK and NULL constraints have been properly created. The SHOW CREATE TABLE statement is useful for displaying the SQL that would regenerate a given table, which is a useful way for checking that FKs have been properly created.

<strong>Examples:</strong>

<table border="0" cellspacing="0" cellpadding="0">

 <tbody>

  <tr>

   <td class="gutter"></td>

   <td class="code"></td>

  </tr>

 </tbody>

</table>

1

<code class="php plain">DROP TABLE IF EXISTS `ENROLLMENT` ;</code>

<table border="0" cellspacing="0" cellpadding="0">

 <tbody>

  <tr>

   <td class="gutter"></td>

   <td class="code"></td>

  </tr>

 </tbody>

</table>

1

2

3

<code class="php plain">DESCRIBE STUDENT;</code>

<code class="php plain">SHOW CREATE TABLE STUDENT;</code>