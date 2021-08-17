---
title: "AI-based Testing Feedback Tool"
chapter: false
weight: 47
pre: "<b>4.7 </b>"
---

## AI-based testing Feedback Tool overview

Artificial Intelligence (AI) makes it possible for software to learn from experience by collecting data, comparing it to the expected output, recognizing patterns, and then making adjustments and adapting.
To improve our UFT One AI model, we need to collect more data. This data consists primarily of snapshots and explanations regarding any misidentifications.

When using AI to inspect your application for objects, you can send feedback directly to Micro Focus.

Let us know how well we identified the objects in your application and help improve the identification in the future.

1.	Click **AI Identification** from the UFT One Toolbar to inspect a screen.

2.	Click **How is the detection? Help us improve** to open the Feedback Tool and send **Micro Focus** feedback about the object identification.

3.	Before you can send any feedback, you must register and log in to the feedback server.

	**Register** to the server once, and use the credentials you set up to log in each time you open the feedback tool.

4. After you log in to the feedback server, you can send Micro Focus feedback about the identification.

	Your feedback does not affect the current object identification in your application.

	It will be considered in future releases of AI-based testing as Micro Focus continues to expand and enhance these capabilities.

5. Mark the object that was not properly identified by AI, Move and resize the highlighted grid to fit the object that you want to mark.

	Enter an object type and press Enter. The object type can be one of the types supported by AI-based testing or a suggestion for a new type.

	See [AI-based testing: Supported control types](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Content/User_Guide/AI-supported-types.htm).

	If your application displays sensitive data that you do not want to include in the feedback that you send, you can blur it using the feedback tool: Click the **Pixelate**  button.

6. If you do not have access to the feedback server, you can save your feedback locally and email it directly to Micro Focus.

7.	Click **SEND FEEDBACK** and Close the Feedback Tool.

## Share Feedback to Micro Focus using AI-based testing Feedback Tool

The below steps are to provide the Feedback using AI-based testing feedback tool for the "MasterCredit" image that was not idenfied when using the **AI Recording**

As prerequisite **REGISTER** on the Feedback server by providing necessary details

1.	Navigate to the below (at Step #2) **"ORDER PAYMENT"** page of the AOS application

2.	Click **AI Identification** from the UFT One Toolbar to inspect the below **"ORDER PAYMENT"** page

	![step 1](/images/40_Create_UFT_AI_Based_Test/feedback.PNG)

3. Click **How is the detection? Help us improve** to open the Feedback Tool and **LOGIN** to the Feedback server

4. Mark the **"MasterCredit"** object not identified by AI and share feedback

	![step 2](/images/40_Create_UFT_AI_Based_Test/master_credit.png)

