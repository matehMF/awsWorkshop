---
title: "Getting Started"
chapter: false
weight: 41
pre: "<b>4.1 </b>"
---

## AI-based testing overview

**UFT One's artificial intelligence (AI) features** enable your tests to interact with the application you are testing in the same way a person would. UFT One uses AI to identify objects visually, based on a wide variety of images, context, and sometimes text.

For example, UFT One's AI can identify many forms of search fields, user profile areas, input fields, buttons, shopping carts and more.

Some advantages of AI-based object identification are:

1. More intuitive test scripts.

2. Tests are technology-agnostic, identifying objects visually, regardless of the UI technology details used behind the scenes.

3. Tests are easier to maintain, as an object changing location, UI framework, or even shape, won’t break the test script as long as the object remains visually similar or its purpose remains clear.


In **UFT One 15.0.2**, the AI features are enabled by default. If you ever need to disable and re-enable them, open **Tools > Options > GUI Testing > AI**, and clear/select the AI active option.


## Open UFT One and create a GUI Test

1. Open UFT One by clicking the icon saved on your desktop, or selecting the following from the Start menu:

	**Micro Focus Unified Functional Testing**

2. In the Add-in Manager window that shows up by default when you start UFT One, ensure that only the **Web Add-in** is selected. Clear all other Add-ins, and then click OK to open UFT One.

	![step 1](/images/40_Create_UFT_AI_Based_Test/add-in_manager.PNG)

3. From UFT One's menu, click **File > New > New Solution**.

4. In the filename field, enter **AdvantageShopping** or any solution name of your choice, and click Create.

	The new AdvantageShopping solution is shown in the Solution Explorer pane.

5. Click **File > Add > New Test**.

6. Select **GUI Test** and enter the test name **AOS_Web**, or any test name of your choice.

	Leave the Location with the default value, and then click **Add**.

	A blank test opens, showing the AOS_Web test flow in the canvas, and another tab with a blank action, named Action1.

	![step 2](/images/40_Create_UFT_AI_Based_Test/action_flow.PNG)

7. Click on the **Action1** tab to continue with the test design

	The AI-based features in UFT One are accessed via the highlighted icons on the UFT One toolbar below:

	![step 3](/images/40_Create_UFT_AI_Based_Test/ai_toolbar_icons.png)
