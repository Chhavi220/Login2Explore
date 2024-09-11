Micro Project Work



Title of the Project : Student Enrollment Form 

Description : Student Enrollment Form that will store data in STUDENT-TABLE relation of SCHOOL-DB database.
Input Fields: {Roll-No, Full-Name, Class, Birth-Date, Address, Enrollment-Date}

Primary key: Roll No.

Benefits of using JsonPowerDB : 
Simplest way to retrieve data in a JSON format.
Schema-free, Simple to use, Nimble and In-Memory database.
It is built on top of one of the fastest and real-time data indexing engine - PowerIndeX.
It is low level (raw) form of data and is also human readable.
It helps developers in faster coding, in-turn reduces development cost.
Release History (release of your JsonPowerDB related code on Github)

Additional you can have: 
JsonPowerDB is a Real-time, High Performance, Lightweight and Simple to Use, Rest API based Multi-mode DBMS. JsonPowerDB has ready to use API for Json document DB, RDBMS, Key-value DB, GeoSpatial DB and Time Series DB functionality. JPDB supports and advocates for true serverless and pluggable API development.

Table of contents:
Roll-No
Student Full Name
Class
Birth-Date
Address
Enrollment-Date
SAVE - INSERT
CHANGE - UPDATE
DELETE
RESET

Illustrations


![image](https://user-images.githubusercontent.com/84792843/221294311-7ab75f8c-d5ee-4fed-92df-43d504a15a65.png)

![image](https://user-images.githubusercontent.com/84792843/221294639-5f04555f-074d-40fd-8bb8-74aef42de642.png)



Scope of functionalities : 

Examples of use : can be used foe various other platforms like Online Examination Registration , Job Application , profile creation , and many more other uses .

Project status : Done

Sources :Introduction to JsonPowerDB - V2.0
https://careers.login2explore.com/course/view.php?id=14

Other information Sources :
https://login2explore.com/jpdb/docs.html

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

STEP BY STEP COURSE DOCUMENTATION :
# JsonPOwerDB
Introduction to JsonPowerDB - V2.0
Login2Xplore 

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creating a Developer Account and Generating Connection Token : -

Visit: http://api.login2explore.com:5577/user/index.html
REGISTER
After registration check your email-id for password.
Login at http://api.login2explore.com:5577/user/index.html using your email and password received.
First of all change password - Left Navigation >> Change Password.
Login with new password. 

Tools > Token > connection token > Generate (Token needed to communicate with Data Base)

90932025|-31949219791851870|90962241

Token used to execute the API

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Installing Talend API Tester : -

Google > settings > Extensions > Chrome Web store > Talend API Tester - Free Edition > Add to chrome extension


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Understanding JsonPowerDB and its Features : -

nimble , schema Free , simple to use , in memory and real time , easy to maintain , serverless support , enables multi mode database , power Index , Web services API
Cost efficient , multiple security layers , best performance

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
JsonPowerDB Use case and Benefits : -

any software app that needs backend db
all rdbms use cases
all document db use cases
all key- value db use cases
use cases that needs GeoSpacial/Time series Analytics
Best suited to real - time application for data analytics
Improving existing application reporting/ analytics performance.
Live working HTML, Templates.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
PUT Command - Creating (Inserting) Record : - # IML (JPDB Index Manipulation Language) 
PUT : Insert single record in the database
Token - 90932512|-31949274757731994|90949158

Talend > post
Base url : http://api.login2explore.com:5577
End-point url : /api/iml (mentioned in command when different)

BODY : 
{
    "token": "90932025|-31949219791851870|90962241",
    "cmd": "PUT",
    "dbName": "Employee",
    "rel": "Emp-Rel",
    "jsonStr": {
        "id": "1",
        "name": "Soniya",
        "email": "soniya@gmail.com",
        "mobileno": "9967825671"
    }
}

> Send >

{"data":"{\"rec_no\":[1]}","additionalData":{"processReqType":0,"dbUpdateFlag":true},
"message":"RELATION CREATED, TEMPLATE CREATED FROM JSON, DATA INSERTED, 
Total 1 rows are inserted, Added 0 columns as New Index Columns.","status":200}

Dashboard > Visualize > Jsondb > select Database and Relation

1	2/24/2023, 8:21:16 PM	soniya@gmail.com	1	9967825671	Soniya

New row - 

{
    "token": "90932025|-31949219791851870|90962241",
    "cmd": "PUT",
    "dbName": "Employee",
    "rel": "Emp-Rel",
    "jsonStr": {
        "id": "2",
        "name": "aniket",
        "email": "aniket@gmail.com",
        "mobileno": "8582887792"
    }
}

{"data":"{\"rec_no\":[2]}","additionalData":{"processReqType":0,"dbUpdateFlag":true},
"message":"DATA INSERTED, 
Total 1 rows are inserted, Added 0 columns as New Index Columns.","status":200}

Dashboard > Visualize > Jsondb > select Database and Relation

1	2/24/2023, 8:21:16 PM	soniya@gmail.com	1	9967825671	Soniya
2	2/24/2023, 8:24:57 PM	aniket@gmail.com	2	8582887792	aniket

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
GET Command - Retrieving Record : - # IRL (JPDB Index Retrieval Language)

Talend - 
Add a project

Name - PUT
Project - JPDB
Service - CRUD
save

GET_BY_KEY : Retrieve single record by json data

Talend > Save as > Name : GET >

POST | http://api.login2explore.com:5577/api/irl

"token": "90932025|-31949219791851870|90962241",

{
    "token": "90932025|-31949219791851870|90962241",
    "dbName": "Employee",
    "cmd": "GET",
    "rel": "Emp-Rel",
    "jsonStr": {
        "name": "aniket"
    }

}


{"data"
:"{\"name\":\"aniket\",\"id\":\"2\",\"mobileno\":\"8582887792\",\"email\":\"aniket@gmail.com\"}"
,"message":"DATA RETRIEVED FROM PI","status":200}


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
UPDATE Command - Update a record : - # IML (JPDB Index Manipulation Language) 

UPDATE : Update multiple records in the database or add a new column in a record

POST | http://api.login2explore.com:5577/api/iml

{
    "token": "90932025|-31949219791851870|90962241",
    "dbName": "Employee",
    "cmd": "UPDATE",
    "rel": "Emp-Rel",
    "jsonStr": {
      "1" : {
        "name": "raju",
      "email" : "raju@gmail.com"
    	}
            "2" : {
      "mobileno":"66666666"
    	}
    }

}


{"data":"{\"1\":{\"name\":\"Soniya\",\"email\":\"soniya@gmail.com\"},\"2\":
{\"mobileno\":\"8582887792\"},\"NewIndexColumnCreated\":0,\"NewNonIndexColumnCreated\":0}","additionalData":
{"processReqType":0,"dbUpdateFlag":true},"message":"Success","status":200}


1	2/24/2023, 8:21:16 PM	raju@gmail.com	1	9967825671	raju
2	2/24/2023, 8:24:57 PM	aniket@gmail.com	2	66666666	aniket
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
REMOVE Command - Remove a record : - # IML (JPDB Index Manipulation Language) - To insert, update and delete Json data.

REMOVE : Remove records from the database

POST | http://api.login2explore.com:5577/api/iml

{
    "token": "90932025|-31949219791851870|90962241",
    "dbName": "Employee",
    "cmd": "REMOVE",
    "rel": "Emp-Rel",
     "record" : 1

}


{"data":"{\"removedRecNos\":[1],\"alreadyRemovedRecNos\":[],\"invalidRecNos\":[]}","additionalData":
{"processReqType":0,"dbUpdateFlag":true},"message":"Success","status":200}


2	2/24/2023, 8:24:57 PM	aniket@gmail.com	2	66666666	aniket

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Ajax Concepts - A Desktop application feel on web-pages ; -

AJAX - Asynchronous JavaScript And XML.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
How to use JsonPowerDB in Web Pages

https://drive.google.com/file/d/1e4VN4PAec-Y1iFsj0BN5j0pM7mfed0VQ/view?usp=sharing

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Creating a Web Project in NetBeans : -



CODE - 

<!DOCTYPE html>
<!--
To change this license header, choose License Headers in Project Properties.
To change this template file, choose Tools | Templates
and open the template in the editor.
-->
<html lang="en">
  <head>
    <title>Bootstrap Example</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link
      rel="stylesheet"
      href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    />
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
  </head>
  <body>
    <div class="container">
      <h2>Vertical (basic) form</h2>
      <form id="empForm" method="post">
        <div class="form-group">
          <span
            ><label for="empId">Employee ID:</label>
            <label id="empIdMsg"> </label
          ></span>

          <input
            type="text"
            class="form-control"
            name="empId"
            id="empId"
            placeholder="Enter Employee ID"
            required
          />
        </div>
        <div class="form-group">
          <label for="empName">Employee Name:</label>
          <input
            type="text"
            class="form-control"
            id="empName"
            placeholder="Enter Employee Name"
            name="empName"
          />
        </div>
        <div class="form-group">
          <label for="empEmail">Email:</label>
          <input
            type="email"
            class="form-control"
            id="empEmail"
            placeholder="Enter Employee Email"
            name="empEmail"
          />
        </div>
        <input
          type="button"
          class="btn btn-primary"
          id="empSave"
          value="Save"
          onclick="saveEmployee();"
        />
      </form>
    </div>

    <script>
      function validateAndGetFormData() {
        var empIdVar = $("#empId").val();
        if (empIdVar === "") {
          alert("Employee ID Required Value");
          $("#empId").focus();
          return "";
        }
        var empNameVar = $("#empName").val();
        if (empNameVar === "") {
          alert("Employee Name is Required Value");
          $("#empName").focus();
          return "";
        }
        var empEmailVar = $("#empEmail").val();
        if (empEmailVar === "") {
          alert("Employee Email is Required Value");
          $("#empEmail").focus();
          return "";
        }
        var jsonStrObj = {
          empId: empIdVar,
          empName: empNameVar,
          empEmail: empEmailVar,
        };
        return JSON.stringify(jsonStrObj);
      }

      // This method is used to create PUT Json request.
      function createPUTRequest(connToken, jsonObj, dbName, relName) {
        var putRequest =
          "{\n" +
          '"token" : "' +
          connToken +
          '",' +
          '"dbName": "' +
          dbName +
          '",\n' +
          '"cmd" : "PUT",\n' +
          '"rel" : "' +
          relName +
          '",' +
          '"jsonStr": \n' +
          jsonObj +
          "\n" +
          "}";
        return putRequest;
      }

      function saveEmployee() {
        // validate form data

        // create JPDB request string - token , dbname , relation name ...

        // Execute this request

        //Reset the form data

        var jsonStr = validateAndGetFormData();
        if (jsonStr === "") {
          return;
        }
        var putReqStr = createPUTRequest(
          "90936861|-31948784479254024|90932362",

          jsonStr,
          "SAMPLE",
          "EMP-REL"
        );

        alert(putReqStr);
        jQuery.ajaxSetup({ async: false });
        /* 
          var resultObj = executeCommand(
          putReqStr,
          "http://api.login2explore.com:5577",
          "/api/iml"
        );

        */

        jQuery.ajaxSetup({ async: true });
        alert(JSON.stringify(resultObj));
        resetForm();
      }
    </script>
  </body>
</html>


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Saving data in JPDB from HTML form :-
![image](https://user-images.githubusercontent.com/84792843/221236356-22fa3e5d-9e1d-4b6e-bead-e28ee931f113.png)

CODE --

<!DOCTYPE html>
<!--
To change this license header, choose License Headers in Project Properties.
To change this template file, choose Tools | Templates
and open the template in the editor.
-->
<html lang="en">
  <head>
    <title>Bootstrap Example</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link
      rel="stylesheet"
      href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    />
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
  </head>
  <body>
    <div class="container">
      <h2>Vertical (basic) form</h2>
      <form id="empForm" method="post">
        <div class="form-group">
          <span
            ><label for="empId">Employee ID:</label>
            <label id="empIdMsg"> </label
          ></span>

          <input
            type="text"
            class="form-control"
            name="empId"
            id="empId"
            placeholder="Enter Employee ID"
            required
          />
        </div>
        <div class="form-group">
          <label for="empName">Employee Name:</label>
          <input
            type="text"
            class="form-control"
            id="empName"
            placeholder="Enter Employee Name"
            name="empName"
          />
        </div>
        <div class="form-group">
          <label for="empEmail">Email:</label>
          <input
            type="email"
            class="form-control"
            id="empEmail"
            placeholder="Enter Employee Email"
            name="empEmail"
          />
        </div>
        <input
          type="button"
          class="btn btn-primary"
          id="empSave"
          value="Save"
          onclick="saveEmployee();"
        />
      </form>
    </div>

    <script>
      function validateAndGetFormData() {
        var empIdVar = $("#empId").val();
        if (empIdVar === "") {
          alert("Employee ID Required Value");
          $("#empId").focus();
          return "";
        }
        var empNameVar = $("#empName").val();
        if (empNameVar === "") {
          alert("Employee Name is Required Value");
          $("#empName").focus();
          return "";
        }
        var empEmailVar = $("#empEmail").val();
        if (empEmailVar === "") {
          alert("Employee Email is Required Value");
          $("#empEmail").focus();
          return "";
        }
        var jsonStrObj = {
          empId: empIdVar,
          empName: empNameVar,
          empEmail: empEmailVar,
        };
        return JSON.stringify(jsonStrObj);
      }

      // This method is used to create PUT Json request.
      function createPUTRequest(connToken, jsonObj, dbName, relName) {
        var putRequest =
          "{\n" +
          '"token" : "' +
          connToken +
          '",' +
          '"dbName": "' +
          dbName +
          '",\n' +
          '"cmd" : "PUT",\n' +
          '"rel" : "' +
          relName +
          '",' +
          '"jsonStr": \n' +
          jsonObj +
          "\n" +
          "}";
        return putRequest;
      }

      function executeCommand(reqString, dbBaseUrl, apiEndPointUrl) {
        var url = dbBaseUrl + apiEndPointUrl;
        var jsonObj;
        $.post(url, reqString, function (result) {
          jsonObj = JSON.parse(result);
        }).fail(function (result) {
          var dataJsonObj = result.responseText;
          jsonObj = JSON.parse(dataJsonObj);
        });
        return jsonObj;
      }

      function resetForm() {
        $("#empId").val("");
        $("#empName").val("");
        $("#empEmail").val("");
        $("#empId").focus();
      }

      function saveEmployee() {
        // validate form data

        // create JPDB request string - token , dbname , relation name ...

        // Execute this request

        //Reset the form data

        var jsonStr = validateAndGetFormData();
        if (jsonStr === "") {
          return;
        }
        var putReqStr = createPUTRequest(
          "90932512|-31949274757731994|90949158",
          jsonStr,
          "SAMPLE",
          "EMP-REL"
        );

        alert(putReqStr);

        jQuery.ajaxSetup({ async: false });
        var resultObj = executeCommand(
          putReqStr,
          "http://api.login2explore.com:5577",
          "/api/iml"
        );
        jQuery.ajaxSetup({ async: true });

        alert(JSON.stringify(resultObj));
        resetForm();
      }
    </script>
  </body>
</html>


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
JPDB using jpdb common js - A Javascript library to make it even easy and fast for developers :-

Code - 

<!DOCTYPE html>
<!--
To change this license header, choose License Headers in Project Properties.
To change this template file, choose Tools | Templates
and open the template in the editor.
-->
<html lang="en">
  <head>
    <title>Bootstrap Example</title>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <link
      rel="stylesheet"
      href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css"
    />
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
    <script src="https://login2explore.com/jpdb/resources/js/0.0.3/jpdb-commons.js"></script>
  </head>
  <body>
    <div class="container">
      <h2>Vertical (basic) form</h2>
      <form id="empForm" method="post">
        <div class="form-group">
          <span
            ><label for="empId">Employee ID:</label>
            <label id="empIdMsg"> </label
          ></span>

          <input
            type="text"
            class="form-control"
            name="empId"
            id="empId"
            placeholder="Enter Employee ID"
            required
          />
        </div>
        <div class="form-group">
          <label for="empName">Employee Name:</label>
          <input
            type="text"
            class="form-control"
            id="empName"
            placeholder="Enter Employee Name"
            name="empName"
          />
        </div>
        <div class="form-group">
          <label for="empEmail">Email:</label>
          <input
            type="email"
            class="form-control"
            id="empEmail"
            placeholder="Enter Employee Email"
            name="empEmail"
          />
        </div>
        <input
          type="button"
          class="btn btn-primary"
          id="empSave"
          value="Save"
          onclick="saveEmployee();"
        />
      </form>
    </div>

    <script>
      function validateAndGetFormData() {
        var empIdVar = $("#empId").val();
        if (empIdVar === "") {
          alert("Employee ID Required Value");
          $("#empId").focus();
          return "";
        }
        var empNameVar = $("#empName").val();
        if (empNameVar === "") {
          alert("Employee Name is Required Value");
          $("#empName").focus();
          return "";
        }
        var empEmailVar = $("#empEmail").val();
        if (empEmailVar === "") {
          alert("Employee Email is Required Value");
          $("#empEmail").focus();
          return "";
        }
        var jsonStrObj = {
          empId: empIdVar,
          empName: empNameVar,
          empEmail: empEmailVar,
        };
        return JSON.stringify(jsonStrObj);
      }

      function resetForm() {
        $("#empId").val("");
        $("#empName").val("");
        $("#empEmail").val("");
        $("#empId").focus();
      }

      function saveEmployee() {
        // validate form data

        // create JPDB request string - token , dbname , relation name ...

        // Execute this request

        //Reset the form data

        var jsonStr = validateAndGetFormData();
        if (jsonStr === "") {
          return;
        }
        var putReqStr = createPUTRequest(
          "90932512|-31949274757731994|90949158",
          jsonStr,
          "SAMPLE",
          "EMP-REL"
        );

        alert(putReqStr);

        jQuery.ajaxSetup({ async: false });
        var resultObj = executeCommandAtGivenBaseUrl(
          putReqStr,
          "http://api.login2explore.com:5577",
          "/api/iml"
        );
        jQuery.ajaxSetup({ async: true });

        alert(JSON.stringify(resultObj));
        resetForm();
      }
    </script>
  </body>
</html>


2	2/24/2023, 10:38:48 PM	payel@gmail.com	61	payel jain

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Useful Commands to Practice
JPDB Documentation Page: http://login2explore.com/jpdb/docs.html#jpdb-command-request 

Practice following commands on the above JsonPowerDB documentation link:

1. IML Commands

PUT
PUT_ALL
UPDATE
REMOVE
2. IRL Commands

GET_BY_KEY
GET_BY_RECORD

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------
