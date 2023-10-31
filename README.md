# Serverless Web Application

<br>
<br>
<br>
<br>


![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/265b0138-4a83-4d99-a78c-a94308f8e277)

<br>
<br>


#### The application architecture uses AWS Lambda, Amazon API Gateway, Amazon DynamoDB, and AWS Amplify Console. Amplify Console provides continuous deployment and hosting of the static web resources including HTML, CSS, JavaScript, and image files which are loaded in the user's browser. JavaScript executed in the browser sends and receives data from a public backend API built using Lambda and API Gateway Finally, DynamoDB provides a persistence layer where data can be stored by the API's Lambda function.


<br>
 




<br>



### 1)	Create a Web App

<br>

      
  1. Create and save the index.html file 

![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/d2436463-1783-4489-9c48-efb908b1a6a7)

 <br>


  2. ZIP (compress) only the HTML file.
  3. In a new browser window, log into the Amplify console.
  4. In the Get Started section, under Host your web app, choose the orange Get started button.
  5. Select Deploy without Git provider. This is what you should see on the screen:

<br>


 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/983a74c6-accf-4111-9fe5-6f8b6e0bd3d4)

<br>

  6. Choose the Continue button.
  7. In the App name field, enter GettingStarted.
  8. For Environment name, enter dev.
  9. Select the Drag and drop method. This is what you should see on your screen

<br>
 
![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/f4acf305-c4b4-4260-ad6c-a31784c97f36)

<br>


 10. Choose the Choose files button.
 11. Select the ZIP file you created in Step 3.
 12. Choose the Save and deploy button.
 13. After a few seconds, you should see the message Deployment successfully completed.

<br>

### Test Your Web App

<br>

 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/e5226afe-3240-41be-80be-dd83c9014544)

<br>

### 2)	Build a ServerLess Function

<br>
 
1. In a new browser tab, log in to the AWS Lambda console.
2. Make sure you create your function in the same Region in which you created the web app in the previous module. 
3. Choose the orange Create function button.
4. Under Function name, enter PowerOfMathFunction.
5. Select Python 3. from the runtime dropdown and leave the rest of the defaults unchanged.

<br>

 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/d1e3f26d-fdae-486e-9843-2ab883b006e1)

<br>


6.  Choose the orange Create function button.
7.  You should see a green message box at the top of your screen with the following message "Successfully created the function PowerOfMathFunction."
8.  Under Code source, replace the code in lambda_function.py

 <br>
 
![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/27832da3-644d-4c4e-8b6a-3a2535a48f9c)

<br>

9.  Save by going to the file menu and selecting Save to save the changes.
10. Choose Deploy to deploy the changes.
11.  Let's test our new function. Choose the orange Test button to create a test event by selecting Configure test event.


<br>

![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/32e25bfa-7670-4da9-96df-a30a5f382949)

 <br>

12. Under Event name, enter PowerOfMathEvent.
13. Change the Jason Objects.

<br>

 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/e9561c4b-344a-4008-a26a-a9f8384679eb)

<br>

### Test your Lambda Function

<br>


 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/164a02b2-2493-4dfa-a201-6d61558fee1d)


<br>


1. Under the PowerOfmath section at the top of the page, select Test tab.
2. You should see a light green box at the top of the page with the following text: Execution result: succeeded. You can choose Details to see the event the function returned.

<br>

### 3) Create a REST API

<br>

  1. Log in to the API Gateway console.
  2. In the Choose an API type section, find the REST API card and choose the Build button on the card.
  3. Under Choose the protocol, select REST.
  4. Under Create new API, select New API.
  5. In the API name field, enter PowerOfMath.
  6. Select Edge optimized from the Endpoint Type dropdown. (Note: Edge-optimized endpoints are best for geographically distributed clients. This makes them a good choice for public services being accessed from the internet. Regional endpoints are typically used for APIs that are accessed primarily from within the same AWS Region.)
  7. Choose the blue Create API button.
  
<br>      
 
![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/3f0ed604-425d-42c9-839d-b6e1e5a6ad3d)

<br>

![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/a1ac30e2-3103-442e-b032-6eadea7f6a88)

<br>

### Deploy API

<br>

1.	In the Actions dropdown list, select Deploy API.
2.	Select [New Stage] in the Deployment stage dropdown list.
3.	Enter dev for the Stage Name.
4.	Choose Deploy.
5.	Copy and save the URL next to Invoke URL 

<br>

### Validate API

<br>

1.	In the left navigation pane, select Resources.
2.	The methods for our API will now be listed on the right. Choose POST.
3.	Choose the small blue lightning bolt.
4.	Paste the following into the Request Body field:

<br>

![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/75fc0552-832c-47ed-ae82-67e1f83d2bb8)

<br>

 5. Choose the blue Test button.
 6. On the right side, you should see a response with Code 200.
 7. We have built and tested an API that calls our Lambda function.

<br>
 
![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/33f5f9da-6d7b-4a6f-ba2c-a2a5e9c6ffbb)

<br>

### 3)	Create a DynamoDB Table
   
  <br>
   
   1.	Log in to the Amazon DynamoDB console.
   2.	Make sure you create your table in the same Region in which you created the web app . 
   3.	Choose the orange Create table button.
   4.	Under Table name, enter PowerOfMathDB.
   5.	In the Partition key field, enter ID. The partition key is part of the table's primary key.
   6.	Leave the rest of the default values unchanged and choose the orange Create table button.
   7.	In the list of tables, select the table name, PowerOfMathDB.
   8.	In the General information section, show Additional info by selecting the down arrow.

<br>

 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/d4c2b27f-72e0-4856-bc93-1b40312fc91e)

<br>

  9.	Copy the Amazon Resource Name (ARN).

<br>

### 4)	Create and Add IAM Policy to Lambda Function.

<br>

   1.	Now that we have a table, let's edit our Lambda function to be able to write data to it. In a new browser window, open the AWS Lambda console.
   2.	Select the function we created.
   3.	We'll be adding permissions to our function so it can use the DynamoDB service, and we will be using AWS Identity and Access Management (IAM) to do so.
   4.	Select the Configuration tab and select Permissions from the right side menu.
   5.	In the Execution role box, under Role name, choose the link. A new browser tab will open.
   6.	In the Permissions policies box, open the Add permissions dropdown and select Create inline policy.
   7.	Select the JSON tab.
   8.	Paste the following policy in the text area, taking care to replace your table's ARN in the Resource field in line 15:

<br>

 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/edf98b0d-e95a-4c40-b616-f051b24451fa)

<br>

   9. This policy will allow our Lambda function to read, edit, or delete items, but restrict it to only be able to do so in the table we created.
   10. Choose the blue Review Policy button.
   11. Next to Name, enter PowerOfMathDynamoPolicy.
   12. Choose the blue Create Policy button.

<br>

Modify the Lambda Function to write DynamoDB table.

<br>


![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/463e50f6-73ba-41c8-89c3-754e9a803be9)

<br>

### Test The Changes

<br>

  1.	Choose the orange Test button.
  2.	You should see an Execution result: succeeded message with a green background.
  3.	In a new browser tab, open the DynamoDB console.
  4.	In the left-hand navigation pane, select Tables > Explore items.
  5.	Select PowerOfMathDatabase, which we created earlier in this module.
  6.	Select the Items tab on the right.
  7.	Items matching your test event appear under Items returned. If you have been using my example the item ID will be 16
  8.	Every time your Lambda function executes, your DynamoDB table will be updated. If the same name is used, only the time stamp will change.

<br>

 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/3dc5d559-5de2-40a2-96c1-076fa12e40a8)

<br>

### 5)	Add Interactivity to Web App

<br>

  1.	Open the index.html file that we have created.
  2.	Replace the existing code with the following:

<br>

 ![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/5eb833ec-cdb4-40c7-a303-59adf9a27bb8)

<br>

Make sure you add your API Invoke URL on Line 60.

<br>

  4. Save the file.
  5. ZIP (compress) only the HTML file.
  6. Open the Amplify console.
  7. Choose the web app created.
  8. Choose the white Choose files button.
  9. Select the ZIP file you created in Step 5.
 10. When the file is uploaded, a deployment process will automatically begin. Once you see a green bar, your deployment will be complete.

<br>

### Test the Updated App

<br>

  1.	Choose the URL under Domain.
  2.	Your updated web app should load in your browser.
  3.	Fill in the number whatever you prefer and choose the Calculate button.
  4.	You should see the result in pop up window.

<br>

![image](https://github.com/virajmate7776/Serverless-Web-Application/assets/117629972/76b6811c-d86f-491e-aafc-bb9b66a49e17)

 <br>

Congratulations! We have a working web app deployed by Amplify console that can call a Lambda function via API Gateway.




