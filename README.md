# Automated-Onboarding-Azure-Project

# Project Intro

I have been working on some hands on projects in Azure to further build and expand my cloud skills. This project is one of the project ideas inspired by Gwyneth Peña-Siguenza. Big shout out to her for all the incredible content she puts out. I highly recommend her youtube channel for anyone who is looking to advance their career.

The aim of the project is to streamline and automate the process of onboarding a new employee into Azure AD now known as Entra ID, and assigning the user necessary Azure resources. Utilizing Azure Logic Apps, the process is to have the new team member details input into Logic Apps which then creates the user account, adds them to a group and assigns them neccessary roles and permissions. Thereafter, finally sends a welcome email to the manager advising of account creation. I used the HTTP request option, making use of the Thunder Client VSCode extension to trigger the Logic App workflow.

# Project Detail

The resources needed for the project are:

* Azure Account

* Entra ID

* Azure Logic Apps

* Azure Resource Manager

* VSCode and Thunder Client extension

The first step of the project is to have your Azure account and Entra ID tenant set up, once that is set up then we go ahead and create a basic group that we can add our new starter into.

Next line of action is to create our Logic App. In the creation, I selected the consumption-based plan so I'm only paying for whenever the workflow runs. Once the Logic App is deployed, next step is to go into the logic app designer pane and begin creating our app.

To start the workflow, a trigger needs to be selected. I selected the "When a HTTP request is received" trigger. The trigger asks for a JSON Schema which I generated using this site JSON to JSON Schema Converter. and added it to the trigger.

Next step is to create our actions. As earlier stated, we need the Logic App to create the user account, add the user to a group along with necessary roles and access assignment, and finally sending a welcome email to the manager to advise of the account creation.

The first action is to create our user in our Microsoft Entra ID tenant. I filled in the boxes of the create user action by using dynamic content and concat functions to pull data from the JSON in the HTTP request.

<img width="366" alt="Screenshot 2023-10-31 at 22 13 37" src="https://github.com/Asonym100/Automated-Onboarding-Azure-Project/assets/76881506/798eda28-2dee-4643-8c11-937d77aa96ef">

Now with the create user action completed, I moved on to the next action to add the user to the group which I created earlier in my Microsoft Entra ID. To add the user to the group, 2 things are needed. The Group ID which I can grab from the Group details pane, and the User ID. The User ID, like previously in the Create User action, can be grabbed using Dynamic content.

With the user created and added to our specified group, the final step in the workflow was to add the action to send the welcome email to advise of the account creation.

<img width="366" alt="Screenshot 2023-10-31 at 22 14 20" src="https://github.com/Asonym100/Automated-Onboarding-Azure-Project/assets/76881506/cd483172-d885-4a1d-bdcb-6b62db4635e4">

Now with our logic app workflow completed and saved, it's time to put the Thunder Client extension to work in VSCode. I loaded up VSCode and opened the Thunder Client extension, selecting the POST option and pasting the Post URL copied from our HTTP trigger to the POST field. I then added the JSON body of the required parameters that the Logic App requested, and sent the request.

<img width="876" alt="Screenshot 2023-12-16 at 00 22 53" src="https://github.com/Asonym100/Automated-Onboarding-Azure-Project/assets/76881506/dd183ee4-fe0e-4977-950a-9821bdd8754f">

With the request sent, I headed back to Azure Portal to verify that the run was successful. I checked and confirmed the user was indeed created in Entra ID and also made sure the user was in the group specified. I also checked my email to confirm I received the welcome email advising of the account creation.

<img width="689" alt="Screenshot 2023-12-16 at 00 20 21" src="https://github.com/Asonym100/Automated-Onboarding-Azure-Project/assets/76881506/1ba99fec-1fbb-430b-a005-98434d03d96f">

# Conclusion

This mini project was excellent and I had lots of fun building it. The project has helped further my understanding of Entra ID and its services such as Privileged Identity Management (PIM), enabling me to effectively manage, control, and monitor access to important resources. I have also honed my skills in designing automation workflows using Azure Logic Apps, using triggers and actions tailored for specific tasks.


