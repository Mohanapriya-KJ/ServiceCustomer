POST: http://localhost:8080/customer/signup
{
    "email" : "johny@example.com",
    "firstName" : "John",
    "lastName" : "Bro",
    "password" : "secret123"
}

POST: http://localhost:8080/customer/signin
{
    "email" : "johny@example.com",
    "password" : "secret123"
}

POST: http://localhost:8080/customer/createResetPasswordToken/{{customer-id}}

POST: http://localhost:8080/customer/resetPassword
{
    "token": "{{token-value}}",
    "newPassword": "Hello1234"
}

POST: http://localhost:8080/customer/createEmailVerificationToken/{{customer-id}}

GET: http://localhost:8080/customer/verifyEmailToken/{{token-value}}

POST: http://localhost:8080/customer/verifyEmail/{{token-value}}

POST: http://localhost:8080/customer/createCustomerGroup/{{customer-group-name}}

POST: http://localhost:8080/customer/addCustomerToACustomerGroup/{{customer-id}}/{{customer-group-id}}

1) Customer --> CreateCustomer
2) Authenticate Customer (Sign In)
3) Customer --> Create a Token for Resetting Customer's Password
4) Customer --> Reset Customers Password
5) Customer --> Create a Token for Verifying Customer's Email
6) Customer --> Get Customer by Email Verification Token
7) Customer --> Verify Customer's Email
8) CustomerGroup --> Create Customer Group
9) Customer --> Update Customer by ID
   - Add Customer to the Customer Group 

Update APIs using Action:
1) Get the Customer
2) Create an Action List
3) Create an Action
4) Add the Action to the Action List
5) Create the Draft using the Version from Customer and the Action List
6) Pass the JSON Body and Make the API Call