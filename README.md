## Project info  
Project Name :Flight booking app  
Group no.58  
Group member:  
Li Chak Fai 13330710  
Poon Wing Hei 13473260  
Choy Tsz Ho 13163059  
  
## Project file intro  
server.js:Include all the main function of the whole project.First ,the ejs file  will allow the users to access the login page of the booking app.The OAuth are implemented for the users who do not have an account.The simple CRUD function used to handle the user input.All the variable include destination,date and Booking ID are initially set to null since the user does not make  booking.The RESTful CRUD function do the similar things with the simple CRUD.But the RESTful CRUD can test the cases through terminal command.Finally the localhost port will be set as 8099.
  
package.json:Dependencies(express,mongodb,passport,psssport-facebook,express-session,path,body-parser,passport-local,express-formidable,fs)  
  
public: css file,images,intltellnput,js  
  
views: Create.ejs, Delete.ejs,Home.ejs,index,ejs,Login.ejs,Read.ejs,Read_result.ejs,Update.ejs  
  
models: staff.js  
  
## The cloud-based server URL  
https://flight-eexs.onrender.com/login  
  
  
## Operation guide  
  
You may tend to skip the first step if you already install the virtual machine.

1.Download a virtual machine (e.g. Azure ,Oracle VirtualBox etc).  
  
2.Download the file and unzip it.  

3.Redirect the path to ensure the downloaded file is on the correct one.
  
4.Install all the packages that listed in package.json dependencies.  
  
5.Once everything is ready ,type npm start in your virtual box terminal.  
  
6.If you successfully enter the localhost ,it will automatically redirect to login.ejs.

There are 2 options to access the flight booking app,choose either one from step 7 or step 8.
  
7.(option 1)Enter your userID and password to get access to the  
booking website.If you do not have an account ,click on the register button to create your own account.The default username is "admin" and the password is "12345". If the password is not correct.It will pop up a warning message called "Invalid password!".
  
8.(option 2)If you have a Facebook account,click login through facebook button to access the flight booking system .You can login with it since OAuth are supported.  
  
9.After you login successfully, there is a default home page called home.ejs for all four function.  
  
10.First,you will be redirect to create.ejs by clicking the start booking button,you can input the destination by typing the abbreviation of the airport around the world.Then select the date from the calendar.After you finished the booking by clicking the confirm button.It will automatically generate a 3-digit booking ID.

11.After you successfully finished the booking,you will be redirect to read.ejs by clicking the navigate booking button to check your booking. It will display the information like destination airport,date selection and booking ID.

12.If you want to edit the booking .You will be redirect to Update.ejs by clicking the modify booking button. First, enter your booking ID and click the submit button .Then ,it will allow you to change the date and the destination you want by typing at the corresponding blanket.After you finished the modification,click the update button to update the booking.

13.If you are in trouble of your trip, access to delete.ejs to cancel your booking by clicking the change information button.Enter your booking ID and click the submit button,it will display all the information of your ticket.Once you click the delete button ,the ticket will be deleted permanently.

14.Once you finished ,click the logout button to return back to the login page. 

Starting from this part ,this is theRESTful crud ,part you can test  the functions from step 6-14 by typing the curl command in the terminal.There are some test case for testing.

-read existed data
curl -X GET http://localhost:8099/api/read/7 (It will display the deatination and the date of the booking ID is equal to 7)

-create the booking 
curl -X POST https://flight-eexs.onrender.com/api/uploaddata/HKG/12-12-2024(The booking destination Hong Kong International airport and the date is in 12-12-2024 will be created.)

-update destination
curl -X PUT https://flight-eexs.onrender.com/api/updata/Destination/810/HKG( Update booking ID:810  destination from KIX to HKG. )

-update date
curl -X PUT https://flight-eexs.onrender.com/api/updata/Date/810/11-12-2024(Update   booking ID:810 date from 12-12 2024 to 11-12-2024. )

-delete booking
curl -X DELETE https://flight-eexs.onrender.com/api/deletedetail/754(Delete all the information of the booking ID 754.)
