Biometric-SBM
An automatic attendance recorder for the fingerprint biometric device eSSL x990, built using Java Spring Boot. The project stores attendance records in a MySQL database and provides functionality for device management, live data capture, and user management.
Features
1.	Automatic Attendance Recording
o	Captures attendance data from eSSL x990 biometric devices and stores it in a MySQL database.
2.	User Management
o	Add new users to the system.
o	Update user privileges and manage user data.
3.	Device Management
o	Enable or disable biometric devices connected to the system.
o	Capture data from multiple devices in real-time.
4.	Live Attendance Capture
o	Start live data capture from biometric devices and retrieve attendance records instantly.
5.	Data Synchronization
o	Retrieve and store fingerprint data from biometric devices in the database.
________________________________________
Project Structure
css
CopyEdit
Biometric-SBM/

├── src/
│   ├── main/
│   │   ├── java/com/example/biometric/
│   │   │   ├── config/
│   │   │   │   └── DatabaseConfig.java
│   │   │   ├── controller/
│   │   │   │   └── MainController.java
│   │   │   ├── service/
│   │   │   │   ├── AddUsersService.java
│   │   │   │   ├── LiveGetDataService.java
│   │   │   │   └── OndGetDataService.java
│   │   │   ├── model/
│   │   │   │   └── User.java
│   │   │   └── main/
│   ├── resources/
│   │   ├── application.properties
├── pom.xml
└── README.md
________________________________________
Code Modules
1. config/DatabaseConfig.java
•	Creates and initializes the MySQL database if it does not already exist.
•	This file should be run during the initial setup on a new server or device.
2. service/AddUsersService.java
•	Connects to the MySQL database to:
o	Insert new users.
o	Update user privileges.
•	Manages biometric devices by enabling/disabling them.
•	Commits updates to the database.
3. service/LiveGetDataService.java
•	Captures attendance data in real-time from multiple biometric devices.
•	Retrieves and stores the data in MySQL.
•	Disconnects from devices and the database after completing operations.
4. service/OndGetDataService.java
•	Fetches a list of users and their fingerprint data from biometric devices.
•	Synchronizes the data with the MySQL database.
5. controller/MainController.java
•	Provides a centralized interface to control and manage the various features:
o	User management
o	Live attendance capture
o	Data synchronization
o	Device management
________________________________________
Getting Started
1. Prerequisites
•	Java 17 or later
•	Maven 3.8.x
•	MySQL 8.x
•	eSSL x990 biometric device(s)
2. Installation
1.	Clone the repository:
bash
CopyEdit
git clone https://github.com/<your-username>/Biometric-SBM.git
cd Biometric-SBM
2.	Build the project:
bash
CopyEdit
mvn clean install
3.	Update the application.properties file with your MySQL configuration:
properties
CopyEdit
spring.datasource.url=jdbc:mysql://localhost:3306/biometric_db
spring.datasource.username=<your-username>
spring.datasource.password=<your-password>
4.	Run the project:
bash
CopyEdit
mvn spring-boot:run
3. Database Initialization
•	Run the DatabaseConfig.java file to create the required database schema.
________________________________________
Usage
1. Adding Users
•	Use the AddUsersService to add new users and update privileges.
•	Devices can be enabled or disabled via this module.
2. Live Data Capture
•	Start live attendance capture using the LiveGetDataService module.
•	Captures attendance data from connected devices in real-time.
3. On-Demand Data Retrieval
•	Use the OndGetDataService to fetch and synchronize user data (including fingerprint data) from biometric devices.
4. Integrated Operations
•	Use the MainController to manage all the features in one place.
________________________________________
Tech Stack
•	Backend: Java Spring Boot
•	Database: MySQL
•	Dependencies: Maven, Hibernate
•	Device Integration: zk API for eSSL x990
________________________________________
Contributing
1.	Fork the repository.
2.	Create a new branch:
bash
CopyEdit
git checkout -b feature-name
3.	Commit your changes:
bash
CopyEdit
git commit -m "Add feature-name"
4.	Push to the branch:
bash
CopyEdit
git push origin feature-name
5.	Create a pull request.
________________________________________
License
This project is licensed under the MIT License.

