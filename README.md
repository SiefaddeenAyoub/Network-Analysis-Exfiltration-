# AWS Web Application from Scratch

## Objective

We'll go over how to start from scratch and design and develop a basic web application. We'll select five services (Amplify, Lambda, IAM, API Gateway, and DynamoDB) and discuss when and why to utilize each one as well as how to integrate them. We'll develop each service as we go, creating a math web application that is ready for use.

### Skills Learned

- Creating an HTML
- Deploying and Hosting a Web Page
- Creating a Python Lambda Function to implement our math functionality
- Creating a Rest API using API Gateway
- Creating a DynamoDB table to store our results
- Invoking the API Gateway endpoint from the index.html page in Amplify

### Tools Used

- AWS
- Lambda
- AWS Amplify
- API Gateway
- DynamoDB
  

## Steps

1. First, create a text file and save it as an HTML file. Next, open that file in Notepad++.
<img src="https://i.imgur.com/0yyxIWh.png"/>

2. Next, we will upload the simple code into Notepad++ that we just copied and pasted.
<img src="https://i.imgur.com/LYb2taI.png"/>

3. Then, save the code in Notepad++. Afterward, we will compress the index file into a zipped folder so that we can begin deploying it using AWS Amplify.
<img src="https://i.imgur.com/kd0XYMP.png"/>

4. On the AWS homepage, use the search bar to look up AWS Amplify.
<img src="https://i.imgur.com/rrTrfNy.png"/>

5. "Next, scroll down and select 'Get Started' to host the web app.
<img src="https://i.imgur.com/vvlbj0t.png"/>

6. Since you don't have a Git provider, select "Deploy without a Git provider".
<img src="https://i.imgur.com/nVTWJPQ.png"/>

7. Next, name your app and environment. Then, drag the zip file containing the index file we created earlier, and click on "Save and Deploy".
<img src="https://i.imgur.com/E3TRwly.png"/>

8. After deploying, you will see a screen indicating that the deployment was successful, and your domain link will be provided.
<img src="https://i.imgur.com/0QeTXZy.png"/>

9. After right-clicking on your link and opening a new tab, you will see that it works and displays as "To the Power of Math".
<img src="https://i.imgur.com/62noQq8.png"/>

10. Next, open a new tab and navigate to Lambda.
<img src="https://i.imgur.com/r2f34KO.png"/>

11. Now, click on "Create a function" on the Get Started tab.
<img src="https://i.imgur.com/m9YuYEU.png"/>

12. Here, click on "Author from scratch", specify a function name, set Python to the latest version (which for us is 3.12), and then scroll down and click "Create function".
<img src="https://i.imgur.com/quTrOKX.png"/>

13. Now, scroll down and replace everything with the provided code.
<img src="https://i.imgur.com/HptcVm5.png"/>

14. Here is the updated code. Press "Ctrl + S" to save it, then click on "Deploy".
<img src="https://i.imgur.com/7TbBOKT.png"/>

15. After successful completion, you should see a green bar at the top indicating success. Next, we need to click on the downward arrow labeled 'Test'.
<img src="https://i.imgur.com/0JuAKAI.png"/>

16. These are the settings you need to configure. Afterward, click on the 'Save' button.
<img src="https://i.imgur.com/3eMxFkf.png"/>

17. Now, run the test and examine the response. If you receive 8.0, the test was successful.
<img src="https://i.imgur.com/wb6mQ2q.png"/>

18. Now, open a new tab and navigate to the AWS homepage. Once there, search for 'API Gateway'.
<img src="https://i.imgur.com/aTBRJlw.png"/>

19. Afterward, scroll down and navigate to the 'Build' section within the REST API category.
<img src="https://i.imgur.com/t6gVtIV.png"/>

20. Create it with everything exactly as shown in the screenshot, then click on 'Create API'.
<img src="https://i.imgur.com/GrtQU40.png"/>

21. Now, click on 'Create Method' located on the right side of the screen.
<img src="https://i.imgur.com/9RaQmFk.png"/>

22. Now, copy everything from the screenshot and begin typing the name, which AWS will autofill with your function.
<img src="https://i.imgur.com/ThRkBUF.png"/>

23. After completing the last step, click on the backslash symbol located above POST, then enable CORS from the right-hand side of your screen.
<img src="https://i.imgur.com/TYToxT5.png"/>

24. Check the Post box. This will enable our Amplify web application to communicate with our Lambda function, as they are hosted on different domains or origins.
<img src="https://i.imgur.com/C5ggMS8.png"/>

25. Now, click on 'Deploy API' and create a new deployment stage named 'dev'. Finally, click on 'Deploy' to finalize the deployment.
<img src="https://i.imgur.com/dYGz8pA.png"/>

26. Then you will be provided with the invoke URL. Ensure to copy it and paste it into a secure note sheet for later reference.
<img src="https://i.imgur.com/QpzNa4Z.png"/>

27. Next, click on the 'Resources' tab on the left-hand side. Then, click on the green 'POST' method. To the far right, you should see 'Test', click on that.
<img src="https://i.imgur.com/U0DBXxJ.png"/>

28. You will now proceed to run this test.
<img src="https://i.imgur.com/Qnnum5H.png"/>

29. If your result is 16, then everything seems to be working correctly so far.
<img src="https://i.imgur.com/UDYVLlq.png"/>

30. Open a new tab and navigate to the AWS homepage. From there, locate and open DynamoDB.
<img src="https://i.imgur.com/3Ccr4fO.png"/>

31. Once you click on DynamoDB, select 'Create table'. Name your table, set the partition key as 'ID', then click on 'Create table' at the bottom.
<img src="https://i.imgur.com/Pxb24le.png"/>

32. After creating the table, click on the table you just created. Then, click on 'Additional info' and copy the ARN into the same notepad sheet from earlier.
<img src="https://i.imgur.com/zp3yBVT.png"/>

33. Now, navigate back to the Lambda tab at the top, if you still have it open, and go to the 'Configurations' tab. Next, click on the hyperlink for the role name.
<img src="https://i.imgur.com/wWlHSFu.png"/>

34. On this page, click on 'Add permissions', then select 'Create inline policy'.
<img src="https://i.imgur.com/hbeuUiy.png"/>

35. Once opened, select JSON next to actions, and then copy the code you see in the screenshot.
<img src="https://i.imgur.com/fj1YuUI.png"/>

36. Next, replace the existing ARN in the 'Resource' section with the ARN you saved earlier for your table.
<img src="https://i.imgur.com/69aPzk7.png"/>

37. Then, click 'Next', name the policy, and finally, click on 'Create policy'.
<img src="https://i.imgur.com/NPcm0c5.png"/>

38. Then, return to your Lambda screen and navigate to the 'Code' section. Remove the current code present there and input the new code.
<img src="https://i.imgur.com/wwFVwth.png"/>

39. This is the updated code. Save it, deploy the changes, and then click 'Test'.
<img src="https://i.imgur.com/AjuBcr5.png"/>

40. If your function displays 8 after testing, then it is functioning correctly.
<img src="https://i.imgur.com/Umjht2J.png"/>

41. After returning to DynamoDB, if you click on 'View table details', you will now see the ID string that was just executed.
<img src="https://i.imgur.com/cNxipCB.png"/>

42. "Now, open the index.html file again in Notepad++.
<img src="https://i.imgur.com/WfS93uc.png"/>

43. Now, replace the existing code with our updated final code.
<img src="https://i.imgur.com/zhhf1ss.png"/>

44. Next, retrieve the API Gateway code you saved earlier from your notes and replace the placeholder 'YOUR API GATEWAY ENDPOINT' with it.
<img src="https://i.imgur.com/5eif9Ha.png"/>

45. Then, save the code, close Notepad++, navigate back to your zip file, and delete it. Afterward, use the updated HTML file to create a new zipped file.
<img src="https://i.imgur.com/SiUjJG9.png"/>

46. Then, return to AWS Amplify and simply drag the new zipped file again. It will automatically deploy for you.
<img src="https://i.imgur.com/BBkGzbK.png"/>

47. Now, when you refresh the original tab that previously displayed only a white page with black lettering, it should show this new content, indicating that you have completed all steps correctly.
<img src="https://i.imgur.com/Ugrmz5y.png"/>

48. We are going to enter the numbers, specifically 2 to the power of 8. When we click the 'Calculate' button, the script on our HTML page will call our API Gateway. This action will trigger the Lambda function, which will perform the calculation. The result will then be written to the database. Finally, we will receive a message returned to us in the browser from API Gateway.
<img src="https://i.imgur.com/eVvypws.png"/>

Thanks for following along!





Credits go to Tiny Techincal Tutorials on YouTube!




