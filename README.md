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
