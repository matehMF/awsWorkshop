---
title: "Record UFT One AI-based Tests"
chapter: false
weight: 42
pre: "<b>4.2 </b>"
---

## AI Record Overview

**Supported in UFT One Web and Mobile GUI tests only, in UFT One versions 15.0.2 or later**

Use the **AI Record** to simplify test creation and improve test automation. Following your clicks, the **AI Record** learns objects and creates test steps. The recording result is a resilient test that can run on multiple platforms and environments.

Recording an AI-based step is made up of three parts: **Inspect, Run, and Add.**

**Inspect**: AI Record inspects a web page or mobile application to identify objects you can use in an AI-based test. [For supported object types, see AI-based testing: Supported control types.](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Content/User_Guide/AI-supported-types.htm)

**Run:** Click on an object, and AI Record runs an operation on the application, preparing to add it to the test.

**Add:** AI Record adds the step to the test.

**AI Record** records a default operation for the object according to its type, unless you select a different operation.


## Record an UFT One AI-based Test

The below steps are for recording business flow of logging into the Advantage Online Shopping demo application portal, searching for an item and buying it.

1. Open the web URL [www.advantageonlineshopping.com](https://www.advantageonlineshopping.com/) for the Advantage Online Shopping **(AOS)** demo application in a browser

2. Launch the **AI Record** from the toolbar icon
	UFT One is minimized, and the AI Record toolbar opens at the top of the screen and begins initializing.
	You can drag the AI Record toolbar to any place you want on the screen.

3. Once the AI recording toolbar is displayed, click on the browser that you want to record
	![step 1](/images/40_Create_UFT_AI_Based_Test/ai_record_toolbar.png)

	AI Record inspects the application and highlights the identified objects. Visual elements and texts are highlighted in different colors.

	In UFT One, an **AIUtil.SetContext** step is automatically added to your test.

	In the **Settings** of AI Record toolbar, select the **Visual Elements** and/or **Texts** check boxes to specify the type of object you want to highlight.

	If **AI Record** does not clearly highlight all identified AI objects, do one of the following:

	Click the **Refresh** button to inspect the application again.

	Click the **Settings** button and increase **Delay Time**, so that the tool waits more time before inspecting again. (**Default:** 3s, **Range:** 0-60s)

4. Hover over the **profile** object, select the **click** operation in the tooltip. The below test step gets added to the UFT One Test and launches the login screen

	**AIUtil("profile").Click**

	The AI Record runs the default operation depending on the object type or runs the selected operation. It adds the step to the test only after the operation is successful.

5. After successful completion of the previous step, **AI Record** inspects and identifies the objects on next screen i.e. AOS login screen

	For input fields, search boxes, and combo boxes, the AI Record may prompt you to enter a value for the recorded step.

	You can see the recording progress, step code, recording result, as well as error messages in the toolbar.

	![step 2](/images/40_Create_UFT_AI_Based_Test/aos_login.png)

	Hover over the **Username** and **Password** fields and select **type** operation to enter the input for respective fields

	**Note:** You can create your own user account on Advantage Online Shopping application or use the below user credentials

	**AIUtil("input", "Username").Type "aidemo"**

	**AIUtil("input", "Password").Type "AIdemo1"**

	Hover over the **SIGN IN** button and select **click** operation

	**AIUtil("button", "LOGIN").Click**

	The login to the AOS application should be successful

	**Tip:** If you face problems entering the Username input, pause recording enter the Username as specified above and then continue with the recording

	To pause the recording, click the **Pause** button on the toolbar. You can then click the **Resume** button to resume the recording.

6. During the recording, you can add a **checkpoint**. That means that you can check the existence or state of an object.

	##### To add a checkpoint

	Hover over a highlighted object you want the test to check.

	A tooltip displays, from which you can add a checkpoint for the object.

	Click **Add Checkpoint** in the tooltip.

	Select **Exist** or **Not Exist** to verify existence.

	Select True to check if the state is On or False to check if the state is Off.

	![step 3](/images/40_Create_UFT_AI_Based_Test/exists_notexists.png)

	To confirm successful login, hover over the logged in Username i.e. text block **"aidemo"** and select **Add Checkpoint**, then select **"Exists"** radio button to add checkpoint step

	![step 3](/images/40_Create_UFT_AI_Based_Test/checkpoint.png)

	**AIUtil.FindTextBlock("aidemo").CheckExists True**

	**Note:**

	The checkpoint for verifying existence applies to all **Visual elements** and **Texts**.

	The checkpoint for verifying states applies only to objects with an **On/Off** state, such as toggles, check boxes, and radio buttons.
	
7. Hover over the **Search** icon and select the **Search** operation, enter text “17t” as search keyword

	**AIUtil("search").Search "17t"**

	Keyword search should be successful and display all the items that match the search criteria

	![step 3](/images/40_Create_UFT_AI_Based_Test/keyword_search.png)

8. Click on the **“HP ENVY – 17t touch”** Text block to select the item from the search results

	**AIUtil.FindTextBlock("HP ENVY - 17t Touch").Click**

9. Click on the **"ADD TO CART"** button to add the selected item to the shopping cart

	**AIUtil("button", "ADD TO CART").Click**

10. You can improve the object identification by adding a relation with another object in proximity

	##### To add a relation:

	Hover over a highlighted object you want to identify.

	A tooltip displays, from which you can add a relation for the object.

	Click **"+Relation"** on the tooltip.

	Click on another object in proximity to add the relation.

	If the relation is successfully added, a blue dot appears next to the object you want to identify.

	To remove the added relation, hover over the object you want to identify again and click Remove Relation on the tooltip. The AI Record will validate the object and restore the relation in case that the object becomes invalid.

	**Note:**  You can select only available objects in proximity on the web page or application.

	You cannot add a relation if the object you selected has a circular relation with the object you want to identify. **Circular relation:** A series of objects defined by their proximity to one another, where the last object is defined by its proximity to the first.

	To add a relationship with **"Shopping_Cart"** object identification, hover over the **"Shopping_Cart"** icon, select **"+Relation"** to add relation with **Help** icon next to it and then select **Click** operation

	**AIUtil("shopping_cart", micAnyText, micWithAnchorBelow, AIUtil("help")).Click**

11. Hover over the **Checkout** button and select **Click** operation

	**AIUtil("button", "CHECKOUT ($849.99)").Click**

12. Click on the **NEXT** button in the **ORDER PAYMENT** screen

	**AIUtil("button", "NEXT").Click**

13. To proceed with the **SafePay** payment option, enter the Username, Password and untick the "save changes in profile for future use" (as this will impact the test execution)

	![step 4](/images/40_Create_UFT_AI_Based_Test/order_payment.png)

	**AIUtil("input", "SafePay username").Type "aidemo"**

	**AIUtil("input", "SafePay password").Type "AIdemo1"**

	**AIUtil("check_box", "Save changes in profile for future J59").SetState "Off"**

	Click on the **PAY NOW** button

	**AIUtil("button", "PAY NOW").Click**

	**Also notice that the "MaterCard" option icon in the ORDER PAYMENT screen is not recognized using AI based identification. You can provide feedback about this to Micro Focus R&D team by following the instructions on [Feedback Tool to share about AI based object identication](/40_create_uft_ai_based_test/7_ai_based_testing_feedback_tool.html)**

14. Add a **Checkpoint** to verify successful payment confirmation

	**AIUtil.FindTextBlock("Thank you for buying with Advantage").CheckExists True**

	![step 5](/images/40_Create_UFT_AI_Based_Test/order_confirmation.png)

15. Click on the **profile** icon and select **Sign out** to logout from the AOS application

	**AIUtil("profile", micAnyText, micFromTop, 1).Click**

	**AIUtil.FindTextBlock("Sign out").Click**

16. Stop the recording and you can now view the AI based test script generated for the above steps

	To stop the recording, press the exit button to close the toolbar.

17. Close the browser window

You can update the existing AI based test steps to identify the objects in more unique ways, please refer the Micro Focus [ADM Help](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Content/User_Guide/AI-based-testing-concept.htm#mt-item-0) article for further details