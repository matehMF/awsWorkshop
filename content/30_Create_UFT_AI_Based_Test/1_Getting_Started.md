+++
title = "Getting Started"
chapter = false
weight = 1
+++

## AI-based testing overview

**UFT One's AI Features** enable your tests to interact with the application you are testing in the same way a person would. UFT One uses AI to identify objects visually, based on a wide variety of images, context, and sometimes text.

For example, UFT One AI can identify many forms of search fields, user profile areas, input fields, button, shopping carts and more.

Some advantages of AI-based object identification are: 

1. More intuitive test scripts.

2. Tests are technology agnostic, identifying objects visually, regardless of the UI technology details used behind the scenes.

3. Tests are easier to maintain, as an object changing location, UI framework, or even shape, won’t break the test script as long as the object remains visually similar or its purpose remains clear. 


In this version of **UFT One 15.0.2** release, the AI Features are enabled by default. If you ever need to disable and re-enable them, open **Tools  > Options  > GUI Testing > AI, and clear/select the AI active option.**


## Open UFT One Application and create a GUI Test

1. Open UFT by clicking the icon saved on your desktop, or selecting the following from the Start menu:

	**All Programs > Micro Focus > Micro Focus Unified Functional Testing > Micro Focus Unified Functional Testing**

2. In the Add-ins Manager window that shows by default when you start UFT One, ensure that only the Web Add-in is selected. Clear all other Add-ins, and then click OK to open UFT One.

	![step 1](/images/30_Create_UFT_AI_Based_Test/add-in_manager.PNG)

3. In UFT One, click the New drop-down in the toolbar, and select Solution.

4. In the File name field, enter **AdvantageShopping** or any solution name of your choice, and click Create.

	The new AdvantageShopping solution is shown in the Solution Explorer pane.
	
5. Click the Add drop-down in the toolbar, and select Add New Test.

6. Select to add a GUI Test to the solution, and enter the test name as **AOS_Web** or any test name of your choice.

	Leave the File Location with the default value, and then click Add.

	A blank test opens, showing the AOS_Web test flow in the canvas, and another tab for a blank action, named Action1.
	
	![step 2](/images/30_Create_UFT_AI_Based_Test/action_flow.PNG)

7. Click on Action1 tab to continue with the test design
	
	You can see below highlighted icons on the UFT One toolbar that enable you to use AI based features in UFT One
	
	![step 3](/images/30_Create_UFT_AI_Based_Test/ai_toolbar_icons.png)
	