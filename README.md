This project is focused on developing a Garage Management System using Salesforce. The primary objective is to streamline garage operations, enhance service efficiency, and improve customer experience. The solution aims to digitize and automate tasks related to appointment scheduling, service tracking, billing, and customer feedback. By leveraging Salesforce’s features, the project intends to boost operational efficiency, ensure accurate data management, and support the long-term goals of garage businesses.

# Garage-Management-system
The Garage Management System is a valuable tool for automotive repair facilities, helping them deliver top-notch service, increase operational efficiency, and build lasting customer relationships. With its user-friendly interface and powerful features, GMS empowers garages to thrive in a competitive market while ensuring a seamless and satisfying experience for both customers and staff.
<br/>
## Salesforce
Salesforce is your customer success platform, designed to help you sell, service, market, analyze, and connect with your customers. 

Salesforce has everything you need to run your business from anywhere. Using standard products and features, you can manage relationships with prospects and customers, collaborate and engage with employees and partners, and store your data securely in the cloud. 

**1. Creating Developer Account:**

  Creating a developer org in salesforce. 
  
  1. Go to https://developer.salesforce.com/signup
  2. On the sign up form, enter the following details : 
    - First name & Last name
    - Email
    - Role : Developer
    - Company : College Name
    - County : India
    - Postal Code : pin code
    - Username : should be a combination of your name and company
  This need not be an actual email id, you can give anything in the format :username@organization.com 
  
  Click on sign me up after filling these. 

  **2. Account Activation**
  
  1. Go to the inbox of the email that you used while signing up. Click on the verify account to activate your account. The email may take 5-10mins.
  2. Click on Verify Account
  3. Give a password and answer a security question and click on change password.
  4. Then you will redirect to your salesforce setup page.
  Your Setup page would look like this:
![image](https://github.com/user-attachments/assets/c810a355-7faa-413c-9437-9b8a5399e553)

## Object
**What Is an Object? **
Salesforce objects are database tables that permit you to store data that is specific to an organization. What are the types of Salesforce objects 

  **Salesforce objects are of two types:** 

  **Standard Objects**: Standard objects are the kind of objects that are provided by salesforce.com such as users, contracts, reports, dashboards, etc. 
  
  **Custom Objects**: Custom objects are those objects that are created by users. They supply information that is unique and essential to their organization. They are the heart of any application and provide a structure for sharing data.

  - To Navigate to Setup page: Click on gear icon ? click setup.

  - To create an object: From the setup page > Click on Object Manager > Click on Create > Click on Custom Object.

  - On Custom object defining page: Enter the label name, plural label name, click on Allow reports, Allow search.
  - Click on Save.

For our project we need to create four objects

    Create Customer DetailsObject
    Create Appointment Object
    Create Service records Object
    Create Billing details and feedback Object
![image](https://github.com/user-attachments/assets/e41c50ee-fe55-49b7-a98e-05f7b2403fab)

## Tabs
- Custom tabs for Customer Details, Appointments, Service Records, and Billing Details & Feedback.
- Tabs are displayed for easy navigation and user access.

What is Tab : A tab is like a user interface that is used to build records for objects and to view the records in the objects. 


*Types of Tabs:*


**Custom Tabs**: Custom object tabs are the user interface for custom applications that you build in salesforce.com. They look and behave like standard salesforce.com tabs such as accounts, contacts, and opportunities.

**Web Tabs**: Web Tabs are custom tabs that display web content or applications embedded in the salesforce.com window. Web tabs make it easier for your users to quickly access content and applications they frequently use without leaving the salesforce.com application.

**Visualforce Tabs**: Visualforce Tabs are custom tabs that display a Visualforce page. Visualforce tabs look and behave like standard salesforce.com tabs such as accounts, contacts, and opportunities.

**Lightning Component Tabs**: Lightning Component tabs allow you to add Lightning components to the navigation menu in Lightning Experience and the mobile app.

**Lightning Page Tabs**: Lightning Page Tabs let you add Lightning Pages to the mobile app navigation menu.

Lightning Page tabs don't work like other custom tabs. Once created, they don't show up on the All Tabs page when you click the Plus icon that appears to the right of your current tabs. Lightning Page tabs also don't show up in the Available Tabs list when you customise the tabs for your apps.

I followed these 4 steps to create a custom tab, 
  - (i) Go to setup page >> type Tabs in Quick Find bar >> click on tabs >> New (under custom object tab).
  - (ii) Select Object(Customer Details) >> Select the tab style >> Next (Add to profiles page) keep it as default >> Next (Add to Custom App)  uncheck the include tab .
  - (iii) Make sure that the Append tab to users' existing personal customizations is checked.
  - (iv) Click save.

This image shows custom tabs which we created for our project
![image](https://github.com/user-attachments/assets/e0d4af08-a7b7-4f71-95fb-e715a729f552)

## Building the Lightning App
1. Name: Garage Management Application.
2. Navigation Items: Customer Details, Appointments, Service Records, Billing, Reports, and Dashboards.
3. User Profiles: Assign access to the System Administrator role.

To create a lightning app page:
1. Go to setup page >> search “app manager” in quick find >> select “app manager” >> click on New lightning App.
2. Fill the app name in app details as Garage Management Application >> Next  >>  (App option page) keep it as default  >>  Next  >>  (Utility Items) keep it as default >> Next.
3. To Add Navigation Items
4. Select the items (Customer Details,Appointments, Service records, Billing details and feedback, Reports and Dashboards) from the search bar and move it using the arrow button  >>  Next.
5. To Add User Profiles: Search profiles (System administrator) in the search bar >>  click on the arrow button >>  save & finish.

![LightningApp](https://github.com/user-attachments/assets/cc02b639-bb66-4ad0-bde4-44aa56d94edd)

## Creating Custom Fields
When we talk about Salesforce, Fields represent the data stored in the columns of a relational database. It can also hold any valuable information that you require for a specific object. Hence, the overall searching, deletion, and editing of the records become simpler and quicker. 

Types of Fields:
- Standard Fields 
- Custom Fields 

**Standard Fields:** As the name suggests, the Standard Fields are the predefined fields in Salesforce that perform a standard task. The main point is that you can’t simply delete a Standard Field until it is a non-required standard field. Otherwise, users have the option to delete them at any point from the application freely. Moreover, we have some fields that you will find common in every Salesforce application. They are, 

     - Created By 
     - Owner 
     - Last Modified
     - Field Made During object Creation 

**Custom Fields:** On the other side of the coin, Custom Fields are highly flexible, and users can change them according to requirements. Moreover, each organiser or company can use them if necessary. It means you need not always include them in the records, unlike Standard fields. Hence, the final decision depends on the user, and he can add/remove Custom Fields of any given form.

For this project we create:-
- Customer Details: Phone and email fields.
  ![Fields-Phone Email_marked](https://github.com/user-attachments/assets/5a2145e3-a762-40a4-bf98-2743bb82b5d3)

- Lookup Fields: Link Appointments to Customers, Service Records to Appointments, and Billing Details to Service Records.
- Picklist Fields: Service status (Started, Completed) and payment status (Pending, Completed).
- Formula Fields: Calculate service date from created date.
- Text Fields: Vehicle number plate (10 characters, unique) and customer feedback rating (1 character).
![Fields-Appointments](https://github.com/user-attachments/assets/d2b47d9d-30c1-4574-a81b-ade26231dbbb)
![Fields R -ServiceRecord](https://github.com/user-attachments/assets/ea1fe105-2328-4e53-a6c0-17fe889093c4)
![Fields R -Billing](https://github.com/user-attachments/assets/625889dd-9b4c-4ff9-8c73-b9f1b2e4ab14)




Task 6: Validation Rules
Validation rules are applied when a user tries to save a record and are used to check if the data meets specified criteria. If the criteria are not met, the validation rule triggers an error message and prevents the user from saving the record until the issues are resolved.

Vehicle Number Plate: Must follow a format (e.g., MH12AB1234).
![image](https://github.com/user-attachments/assets/47a27cd8-ab59-41d5-a78c-939c11698b6e)

Service Status: Must be set to "Completed" before record can be saved.
Rating: Customer service rating must be between 1 and 5.
![image](https://github.com/user-attachments/assets/6fcff8a2-fad8-408c-a1bd-f6879382a225)


Task 7: Duplicate Rules
Matching Rule: Checks Gmail and phone number to identify duplicate customer details.
![image](https://github.com/user-attachments/assets/a3ad72da-3f77-45c7-b45e-b83bd677b223)

Duplicate Rule: Prevents duplicate customer records.
![image](https://github.com/user-attachments/assets/a63be590-e53e-4190-a075-59356e5077ed)


Task 8: Profiles
A profile is a group/collection of settings and permissions that define what a user can do in salesforce. Profile controls “Object permissions, Field permissions, User permissions, Tab settings, App settings, Apex class access, Visualforce page access, Page layouts, Record Types, Login hours & Login IP ranges. You can define profiles by the user's job function. For example System Administrator, Developer, Sales Representative. 

Types of profiles in salesforce:
1. Standard profiles: 
  By default salesforce provides below standard profiles. 

        Contract Manager
        Read Only
        Marketing User
        Solutions Manager
        Standard User
        System Administrator.

We cannot deleted standard ones 
Each of these standard ones includes a default set of permissions for all of the standard objects available on the platform. 

2. Custom Profiles: 

Custom ones defined by us. 
They can be deleted if there are no users assigned with that particular one.

Manager Profile: Access to all custom objects with extended session time and password settings.
![image](https://github.com/user-attachments/assets/5c83a22d-5379-4212-8f9c-a4571cc9b50f)

Sales Person Profile: Limited access to objects with tailored permissions.
![image](https://github.com/user-attachments/assets/b940275a-0e2a-436a-a395-73459419bd0a)


Task 9: Roles and Role Hierarchy
A role in Salesforce defines a user's visibility access at the record level. Roles may be used to specify the types of access that people in your Salesforce organization can have to data. Simply put, it describes what a user could see within the Salesforce organization.

Manager Role: Directly under the CEO.
Sales Person Role: Reports to the Manager role.
![image](https://github.com/user-attachments/assets/2ac89ba6-a938-4ea4-9205-06a42755bebc)


Task 10: Users
A user is anyone who logs in to Salesforce. Users are employees at your company, such as sales reps, managers, and IT specialists, who need access to the company's records. Every user in Salesforce has a user account. The user account identifies the user, and the user account settings determine what features and records the user can access.

Manager User: Role as Manager, Profile as Manager, Salesforce license.
![image](https://github.com/user-attachments/assets/4fa2df61-ed15-48d6-a2c3-cc8301e8c483)


Sales Person Users: Role as Sales Person, Profile as Sales Person, Salesforce Platform license.
![image](https://github.com/user-attachments/assets/355f5dba-f79e-4ac7-92d8-dda207c57f45)



Task 11: Public Groups
Public groups are a valuable tool for Salesforce administrators and developers to streamline user management, data access, and security settings. By creating and using public groups effectively, you can maintain a secure and organized Salesforce environment while ensuring that users have appropriate access to the resources they need.

Sales Team Group: Contains all Sales Person roles for sharing access.
![image](https://github.com/user-attachments/assets/ff2b7a75-4e29-4c29-9e83-aa4375065193)


Task 12: Sharing Settings
Service Records OWD: Set to Private.
Sharing Rule: Grants read/write access to Manager for Sales Person’s service records.


Task 13: Flows
Record-Triggered Flow: Automates updates and email alerts for billing completion.
Email Alert: Sends a "Thank you" message when payments are completed.


Task 14: Apex Triggers
Handler Class (AmountDistributionHandler): Calculates service amounts based on selected services.
Trigger (AmountDistribution): Runs on appointment insert or update to update service amounts.


Task 15: Reports
Report Folder: Organize all reports under "Garage Management Folder".
Custom Report Type: Combines Customer Details, Appointments, Service Records, and Billing.
Reports: Custom report "Service Information Report" with fields for customer, appointment date, service status, and payments.


Task 16: Dashboards
Dashboard Folder: "Service Rating Dashboard" for organizing dashboards.
Dashboard Components: Visualizes service ratings, payment statuses, and operational KPIs.


Conclusion
The Garage Management System built on Salesforce provides a comprehensive platform for managing appointments, services, and billing. Through the use of custom objects, tabs, profiles, flows, validation rules, and Apex triggers, the system ensures smooth operations, efficient record management, and enhanced customer satisfaction. This project enables better tracking of garage operations, fosters data-driven decision-making, and supports the long-term growth of garage businesses.
