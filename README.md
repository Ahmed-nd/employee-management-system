# Employee Management System

Employees are the backbone of any company therefore their management plays a major role in deciding the success of an organization. Employees Management Software makes it easy 
for the employer to keep track of all records. This software allows the administrator to edit employees, add new employees, update /delete employees. Each employee in the database is associated with a department can be added and edited when need arises. Employees can be transferred between departments easily without having to retype back their information in the database. 
A flexible and easy to use Employee Management software solution for small and medium sized companies provides modules for personnel information management thereby organization. This system brings about an easy way of maintaining the details of employees working in any organization, It is simple to understand and can be used by anyone who is not even familiar with simple employees system, It is user friendly and just asks the user to follow step by step operations by giving easy to follow options, It is fast and can perform many operations for a company. 
## The goal of this project
Is to design and develop an employee management system to fill existing gaps in the electronic management of employees.

## Technical detail:
We used file stream library to handle files. It provides us with very useful functions like read, 
write, seekg, tellg, clear etc.
### The system project use three physical files: 
 

- Data file: contains all Employee record fields [Serial, First Name, Last Name, Age, Department, and Salary].
  - Data file: variable length-based record with variable length-based field, and starting with 2-bytes for avail-list header followed by records.
  - Record size(2-bytes) field size(2-bytes) Serial (5-bytes) Field size (2-bytes) First Name field size (2-bytes) Last Name field size (2-bytes) Age (2-bytes) field size (2 bytes).
- Primary Index file: contains the employee Serial, and record offset (starting byte at the data file).
  - Primary Index file: fixed-length fields (7 bytes per record).
  - records (5 bytes for Serial + 2 bytes for offset).
- Secondary Index file: contains the employee Department, and Serial. The Avail-List has been implemented in the Data file, so a 2-byte header field has been added at the beginning of data file Data file is named as project.txt, the primary index file is named as index1.txt and the secondary Index file as index2.txt.
Department field size(2-bytes) Salary (4-bytes)
  - Secondary Department Index file: fixed-length fields (15 bytes per record)
  - records (10 bytes for Department + 5 bytes for Serial)

## Employee Management System Features
1. Add New Employee:
This function used to add a new employee taken from user.
User input all the employee attributes.
And the add function check the avail list if there are deleted record its size equal the 
new one or less it replace the deleted employee with the new one using the First fit 
strategy 
But if there is no deleted slots or fit ones the function behave normally (put the new 
record at the end of file

![image 1](https://user-images.githubusercontent.com/62723180/127905006-54953289-f534-428f-befc-aaf76eede3d0.png)

And it saved like that:

![image 2](https://user-images.githubusercontent.com/62723180/127905026-482423ea-665b-4a92-80c7-5720cff1ada4.png)

2. Update Employee:
This function update record that user has entered its serial number until the new record fits and update the new department in secondary index file. 
3. Delete Employee:
This function delete record that user has entered its serial number and mark that record with a (*) and refer to the next deleted record
Secondary index doesn’t change but in primary index record removes.
And avail list will be updated by adding the new deleted record on the file.
4. Display All Employees:
It displays all records using primary index.
5. Display all Employees in a Specific Department
This function search for a Specific Department and display all the record that have the 
same department.

![image 3](https://user-images.githubusercontent.com/62723180/127905044-95b80dce-db1c-42eb-bb82-5570513c60b1.png)

6. Search Employee by Serial:
This function take a serial and display the record that have this serial
If it is not found the system will display error massage 

## Conclusion
The project is to digitalize the database of Employees in organizations and enabling Administrators to have benefit from computers. Software acts as an Information System between Employees and Administrators. Software provides Employees management System for inserting, 
Searching and deleting records will ease and simplicity. We will provide a fresh new approach to our esteemed users to search for records and make databases in a digital way.
## Resources
Book: File Structures An Object-Oriented Approach with c++
