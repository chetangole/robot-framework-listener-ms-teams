# Robot Framework Listener for Microsoft Teams
Send notification of your Robot test suit execution to a configured Microsoft Teams channel in real time. 

## Why use this listener
While using Robot Framework for our daily test automation, I realised that checking the result of test execution isn't easy task, you need to login into the Jenkins and search for the report. There was a need to automate the way we see the results. 

## What this listener does?
- Automated report generation without logging into the Jenkins Server. All the reports will be available in a configured Microsoft Teams channel with color coding and statistics about failed and passed test cases.
- If the test automation is very huge, the Jenkins reports are usually available only after the complete execution. Using this listener you will be able to see the reports of your test suit execution as soon as each suit completes. 
### Screenshot of the Microsoft Teams Card
![Screenshot](/screenshot.png?raw=true "Screenshot of Successful Result")

## How to install this listener
### Prerequisite
- Python with required libraries as specified in requirements.txt
- Robot Framework with test files
- Incoming webhook for Microsoft Teams Channel. Please see [official Microsoft Documentation to create an incoming webhook](https://docs.microsoft.com/en-us/microsoftteams/platform/webhooks-and-connectors/how-to/add-incoming-webhook)
- The listener expects certain values in environment variable. 
  - WEBHOOK_URL=\<URL generated from step 1\>
  - BUILD_URL= \<Standard Jenkins environment variable\>
  - BUILD_NUMBER= \<Standard Jenkins environment variable\>

### Installation
Robot Framework has a listener interface that can be used to receive notifications about test execution. You can simply include the file as a part of your listener using below command while executing the test. You can read more about how to use listener in [official documentation of Robot Framework](https://robotframework.org/robotframework/latest/RobotFrameworkUserGuide.html#listener-interface).

```
robot --listener path/to/ms_teams_listener.py tests.robot
```

## FAQ
* What is Robot Framework?

Robot Framework is a Python-based, extensible keyword-driven automation framework for acceptance testing, acceptance test driven development (ATDD), behavior driven development (BDD) and robotic process automation (RPA). Fead more: https://robotframework.org/
* What is Microsoft Teams?

Microsoft Teams is a proprietary business communication platform developed by Microsoft, as part of the Microsoft 365 family of products. Read More: https://www.microsoft.com/en-in/microsoft-teams/group-chat-software
