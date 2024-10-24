To Supply Leftover Food to Poor:-
DEMO VIDEO:-  https://drive.google.com/file/d/1RaGIMnrkHxJtEI5CmT2qgPxmeIaB9zy3/view?usp=sharing


              To Supply Leftover Food to Poor 
Project Overview:-
Food Connect :- It is designed to manage food donation events, distribution, and logistics by leveraging Salesforce's CRM capabilities. It helps track donors, volunteers, venues, and resources while automating workflows like event scheduling, communication, and reporting to ensure efficient coordination of food donation and distribution efforts.
 
Objects :-
Venue Object :- Venue: Used to manage and track event locations for food donation and distribution in the Food Connect project.
Drop-Off Point Object :- Drop-Off Point: Used to manage and track designated locations for food donations in the Food Connect project.
Task Object :- Task: Used to manage and track activities and responsibilities related to food donation events in the Food Connect project.
Volunteer Object :- Volunteer: Used to manage and track individuals who assist with food donation events and activities in the Food Connect project.
Execution Details Object :- Execution Detail: Used to manage and track specific operational details and progress of food donation events in the Food Connect project.
Tabs :-
Venue Tab: The Venue tab provides users with quick access to manage and view all Venue records, allowing them to efficiently track locations for food donation and distribution events in the Food Connect project.
Drop-Off Point Tab: The Drop-Off Point tab allows users to access and manage designated locations for food donations, helping streamline the logistics of donation collection.
Task Tab: The Task tab provides users with an organized view of tasks and activities related to food donation events, enabling better coordination and assignment of responsibilities.
Volunteer Tab: The Volunteer tab helps users manage and track volunteer involvement, ensuring efficient allocation of volunteers for various food donation activities.
Execution Detail Tab: The Execution Detail tab allows users to monitor and record detailed operational data for food donation events, supporting event execution and progress tracking.
 

Lightning App :- 
1.	App Name: FoodConnect
2.	Developer Name: FoodConnect
3.	Image: Optional
4.	Primary Color Hex Value: Default
5.	Navigation Style: Standard Navigation
6.	Utility Items: Default (no custom utility items added)
7.	Navigation Items:
o	Home
o	Venue
o	Drop-Off Point
o	Task
o	Volunteer
o	Execution Details
o	Reports
8.	User Profile: System Administrator
Field and Relationships:-
Lookup Relationship (Volunteer to Drop-Off Point):
Allows volunteers to be associated with multiple drop-off points flexibly without enforcing strict dependencies.
Master-Detail Relationship (Execution Details to Volunteer):
Ensures that execution details are tied to a specific volunteer, enforcing data integrity and cascading deletions.
Master-Detail Relationship (Execution Details to Task):
Maintains a dependency where execution details cannot exist without an associated task, ensuring task context.
Lookup Relationship (Drop-Off Point to Venue):
Provides flexibility for drop-off points to be associated with multiple venues without enforcing strict dependencies.
Lookup Relationship (Task to Venue - Sponsored By):
Allows tasks to have an optional association with a venue for sponsorship without enforcing task existence.
Lookup Relationship (Task to Drop-Off Point):
Enables tasks to optionally connect with drop-off points, accommodating tasks that may not have a designated location.
Flow:- The flow is designed to automate the process of creating records in the Venue object, ensuring efficient data entry and enhancing user experience. The following components are used in this flow:
•	Screen Flow:
This type of flow allows for user interaction, enabling users to input data in a structured format.
Components and Their Purpose:
•	Screen Element (Venue Details):
This element serves as the interface where users provide essential information about the venue.
•	Text Component (Venue Name):
Captures the name of the venue, which is crucial for identification.
•	Email Component (Contact Email):
Collects the email address for primary contact, facilitating communication regarding venue-related matters.
•	Phone Component (Contact Phone):
Gathers a contact phone number to ensure direct communication can occur if needed.
•	Text Component (Venue Location):
Allows users to specify the physical address or location of the venue, essential for logistical planning.
•	Number Component (Latitude):
Captures the latitude of the venue, which can be used for mapping and location services.
•	Number Component (Longitude):
Captures the longitude of the venue, completing the geographical coordinates necessary for precise location identification.
•	Create Record Element (Create Venue Record):
This element is responsible for saving the venue information into the database, ensuring all inputted data is stored correctly.
 


Trigger:-
Creating a trigger in Salesforce allows you to automate processes and enforce business logic by executing specific actions when records in the Drop-Off Point object are created, updated, or deleted. This functionality ensures data integrity and enhances appli cation responsiveness based on user interactions with the object. 

Profiles:-
To create a custom profile for specific user access and permissions. NGOs Profile.
Creation of User1
•	Purpose: To create a new user in Salesforce with specific details tailored for NGO use.
•	User Details:
o	First Name: Iksha Foundation
o	Last Name: Iksha_Foundation
o	Alias: iiksh
o	Email: iiksh@gmail.com
o	Username: ikshafoundation@sb.com (ensure it's unique)
o	Nickname: Auto Populated
o	User License: Salesforce Platform
o	Profile: NGOs Profile
o	Active: Checked
This user will be configured to have access tailored for nonprofit operations.
User2:NSS User3:Street_cause
 
Report Types:-To generate custom reports that provide insights on relationships between Venues, Drop-Off Points, and Volunteers.
•	Keywords:
o	Primary Object: Venues
o	Report Type Label: Venue with DropOff with Volunteer
o	Report Type Name: Venue_with_DropOff_with_Volunteer
o	Store in Category: Other Reports
o	Deployment Status: Deployed
o	Related Objects: Drop-Off Points, Volunteers
o	Relationship Option: "A" records may or may not have related "B" records
This report type helps create comprehensive reports combining data from Venues, Drop-Off Points, and Volunteers, enabling effective data analysis for nonprofit activities.
Reports:-
Creation of Report on Venue with DropOff with Volunteer
•	Purpose: To generate a custom report showing relationships between venues, drop-off points, and volunteers.
•	Report Name: venue and Drop Off point
•	Report Type: Venue with DropOff with Volunteer
•	Group Rows by: Volunteer Name
•	Columns: Venue Name, Drop-Off point Name, Distance
•	Folder: Custom Reports
This report helps track and analyze volunteer activities across venues and drop-off points, facilitating operational management for nonprofits.
 
Creation of Report on Volunteers with Execution Details and Tasks
•	Purpose: To generate a detailed report showing volunteer tasks, execution details, and performance ratings.
•	Report Name: Volunteer Task
•	Report Type: Volunteers with Execution Details and Tasks
•	Group Rows by: Volunteer ID
•	Columns: Volunteer Name, Task Name, Execution Detail Name, Volunteer Owner Name, Task Date, Task Rating
•	Folder: Custom Reports
 
 
Adding venue and Drop Off point Report to the Dashboard:-
•	Purpose: To visualize the "Venue and Drop Off Point" report data on a custom dashboard.
•	Dashboard Name: Organization Details
•	Folder: Custom Dashboards
•	Report Selected: venue and Drop Off point Report
•	Display As: Lightning Table
•	Component Theme: Dark (Optional)
This allows real-time tracking of venue and drop-off point activities, making it easier to monitor and manage operations from the dashboard.
 
Adding "Volunteer Task" Report to the Dashboard
•	Purpose: To visualize the "Volunteer Task" report on the dashboard for task tracking and performance analysis.
•	Report Selected: Volunteer Task Report
•	Display As: Line Chart
•	Component Theme: Dark (Optional)
This setup provides a visual representation of volunteer tasks, aiding in monitoring task completion and volunteer performance efficiently on the dashboard.
 
Creation of Sharing Rules
•	Purpose: To control and manage access to Drop-Off point records based on distance criteria for different user groups.
•	Rules:
o	Rule 1: Share Drop-Off points with a distance of less than 15 units with the "Iksha" Public Group.
o	Rule 2: Share Drop-Off points with a distance between 15 and 30 units with the "NSS" Public Group.
o	Rule 3: Share Drop-Off points with a distance between 30 and 50 units with the "Street Cause" Public Group.



Home Page:-
 

Conclusion:-
The creation of a custom Home Page for the FoodConnect App integrates essential components like the Venue Flow and the Dashboard, providing users with a streamlined interface to manage key functionalities. By customizing the home page layout with these interactive elements, users can easily access reports, flows, and key organizational data, enhancing productivity and user experience within the FoodConnect application.










