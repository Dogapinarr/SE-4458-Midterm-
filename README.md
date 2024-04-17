# SE-4458-Midterm-
Mobile Provider Billing API
This project implements a RESTful API for a mobile provider company, facilitating various operations related to billing, user management, and authentication.

Endpoints
User Authentication
Endpoint: /v1/login

Method: POST

Parameters:

subscriber_no: Subscriber number
password: User password
Response:

If authentication succeeds, returns an access token.
If authentication fails, returns an error message.
Query Bill
Endpoint: /v1/query-bill

Method: GET

Authorization: JWT Token

Parameters:

subscriber_no (optional): Subscriber number (for admin, it can be used to query bills of other subscribers)
month: Billing month
Response:

Returns the total bill amount and payment status for the specified month.
Query Detailed Bill with Pagination
Endpoint: /v1/query-bill-detailed

Method: GET

Authorization: JWT Token

Parameters:

subscriber_no (optional): Subscriber number (for admin, it can be used to query bills of other subscribers)
month: Billing month
page (optional): Page number for pagination (default is 1)
Response:

Returns detailed bill information (total amount and details) for the specified month with pagination support.
Query Unpaid Bills (for Banking App Integration)
Endpoint: /v1/banking-app/query-bill

Method: GET

Authorization: JWT Token

Parameters:

subscriber_no (optional): Subscriber number (for admin, it can be used to query bills of other subscribers)
Response:

Returns a list of unpaid bills for the specified subscriber.
Pay Bill
Endpoint: /v1/website/pay-bill

Method: POST

Parameters:

subscriber_no: Subscriber number
month: Billing month
Response:

If the bill is successfully paid, returns a success message.
If the bill is already paid or not found, returns an error message.
Admin - Add Bill
Endpoint: /v1/website/admin/add-bill

Method: POST

Authorization: JWT Token (Admin)

Parameters:

subscriber_no: Subscriber number
month: Billing month
total: Total bill amount
details: Bill details
paid_status: Payment status (boolean)
Response:

Adds a bill to the database and returns a success message.


Technologies Used:
Flask: Python web framework for building APIs.
SQLite: Lightweight relational database for storing data.
Flask JWT Extended: Flask extension for JSON Web Tokens.
Flask Swagger UI: Flask extension for adding Swagger UI for API documentation.

Swagger: http://localhost:5000/swagger/


Versioning:
This project follows a versioning scheme to ensure backward compatibility and facilitate changes over time. The current version is v1. The version is included in the endpoint URLs to allow for future updates without breaking existing client applications.


Getting Started:
Install Flask, Flask-JWT-Extended, Flask-Swagger-UI, and SQLite3.
Clone the repository.
Navigate to the project folder in the terminal.
Run the Flask application by executing python app.py.
Access the API endpoints using tools like Postman or curl.


Data Model :


![image](https://github.com/Dogapinarr/SE-4458-Midterm-/assets/147092474/20e5c12c-1f89-4854-9a97-b452bf997005)



Video Presentation :

https://drive.google.com/file/d/1zVj9PF0hSuVGiKRWHZZFfGluDQFciodx/view?usp=sharing
