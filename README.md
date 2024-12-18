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
- Customer Details: Phone and email fields.
- Lookup Fields: Link Appointments to Customers, Service Records to Appointments, and Billing Details to Service Records.
- Picklist Fields: Service status (Started, Completed) and payment status (Pending, Completed).
- Formula Fields: Calculate service date from created date.
- Text Fields: Vehicle number plate (10 characters, unique) and customer feedback rating (1 character).


Task 6: Validation Rules
Vehicle Number Plate: Must follow a format (e.g., MH12AB1234).
Service Status: Must be set to "Completed" before record can be saved.
Rating: Customer service rating must be between 1 and 5.
Task 7: Duplicate Rules
Matching Rule: Checks Gmail and phone number to identify duplicate customer details.
Duplicate Rule: Prevents duplicate customer records.
Task 8: Profiles
Manager Profile: Access to all custom objects with extended session time and password settings.
Sales Person Profile: Limited access to objects with tailored permissions.
Task 9: Roles and Role Hierarchy
Manager Role: Directly under the CEO.
Sales Person Role: Reports to the Manager role.
Task 10: Users
Manager User: Role as Manager, Profile as Manager, Salesforce license.
Sales Person Users: Role as Sales Person, Profile as Sales Person, Salesforce Platform license.
Task 11: Public Groups
Sales Team Group: Contains all Sales Person roles for sharing access.
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
