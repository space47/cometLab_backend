Before going through the below material.
If u want to test the API easily and with an UI then please copy whole code of swagger.yaml file from the repo. and paste it in the editor of this url https://editor.swagger.io/  . It will generate the UI of the All endpoints u can test the API there. 
Then after pasting the code.
On clicking any endpoint click on try it out on the right to test it, then execute after entering ur body
After register and login, paste the token generated as a response in the field which will be open on clicking the Authorize button in the Swagger UI.
Now you can access the endpoints which are restricted for the participants. 

There are total to 9 routes.
Server is hosted at https://comet-lab-backend.vercel.app/

Auth Routes
'/api/v1/auth/login' -- for login (POST REQUEST)
'/api/v1/auth/register' -- for register (POST REQUEST)

Question Routes
'/api/v1/questions' -- for adding problem  (POST REQUEST)   -- only admin can access
'/api/v1/questions' -- for fetching all problem (GET REQUEST)   -- unauthenticated route
'/api/v1/questions/:problemId' -- for fetching all problem (GET REQUEST) -- unauthenticated route
'/api/v1/questions/:problemId' -- for updating problem  (PATCH REQUEST)  --- only admin can access
'/api/v1/questions/:problemId' -- for deleting problem (DELETE REQUEST)  ---only admin can access

TestCase Routes
/api/v1/testCases -- for fetching all test case (GET REQUEST)  -- only admin can access
/api/v1/testCases -- for adding test case (POST REQUEST)       -- only admin can access

Submission Route
'/api/v1/submission' -- for submission of solution (POST REQUEST) -- only authenticated user can access

-I used bcryptjs for encrypting the password.
-JWT for token generation
-As guided token is valid for 1 day
-MongoDB for storing the question and user details.
-Only question is stored in the DB.
-Added pagination to the route. Route /api/v1/questions only 10 question in one page
-I have used code refactoring for easy modification by using routers, controllers.
-Some security library are also used.
-Created separate controllers for each routes, for auth, question, testCase, submission
-Created middleware to distinguish b/t admin and participants and for user token verificaton.
-Crated a differnet file for code structure for sending e-mail. Using ethereal mail service.
-U have to paste auth object from your ethereal account in my /utils/nodemailerconfig file to see mail in ur inbox folder.
-Created multiple file to handle differet type of errors.


Problem Faced-- Unbale to host the swagger Ui because vercel is not allowing it.
                Docgen is also not working in vercel when using it to host with express.static.
                Used vercel because it is fast and not heroku because it needs credit card.



Please provide the feedback of the assinment.




