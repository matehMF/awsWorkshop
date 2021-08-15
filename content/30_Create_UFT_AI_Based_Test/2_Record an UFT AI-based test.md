+++
title = "Record an UFT AI-based test"
chapter = false
weight = 2
+++

## AI Record Overview

**Supported on GUI UFT Mobile and Web tests only, in UFT One versions 15.0.2 and later**

Use the **AI Record** to simplify test creation and improve test automation. Following your clicks, the **AI Record** learns objects and creates test steps. The recording result is a resilient test that can run on multiple platforms and environments.

Recording an AI-based step is made up of three parts: **Inspect, Run, and Add.**

**Inspect**: AI Record inspects a web page or mobile application to identify objects you can use in an AI-based test. [For supported object types, see AI-based testing: Supported control types.](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Content/User_Guide/AI-supported-types.htm)

**Run:** Click on an object, and AI Record runs an operation on the application, preparing to add it to the test.

**Add:** AI Record adds the step to the test.

**AI Record** records a default operation for the object according to its type, unless you select a different operation.


## Record an UFT AI-based Test

The below steps are for recording business flow of loging into the Advantage Online Shopping demo application portal, search for an item and buying it. 

1. Open the web URL https://www.advantageonlineshopping.com/ for Advantage Online Shopping **(AOS)** demo application in a browser

2. Launch the **AI Record** from the toolbar icon
	UFT One is minimized, and the AI Record toolbar opens at the top of the screen and begins initializing.
	You can drag the AI Record toolbar to any place you want on the screen.

3. Once the AI recording toolbar is displayed, click on the browser that you want to record
	![step 1](/images/30_Create_UFT_AI_Based_Test/ai_record_toolbar.png)
	
	AI Record inspects the application and highlights the identified objects. Visual elements and texts are highlighted in different colors.
	
	In UFT One, an **AIUtil.SetContext** step is automatically added to your test.
	
	In the **Settings**  of AI Record toolbar, select the **Visual Elements** and/or **Texts** check boxes to specify the type of object you want to highlight.
	
	If **AI Record** does not clearly highlight all identified AI objects, do one of the following:
	
	Click the **Refresh** button to inspect the application again.
	
	Click the **Settings** button  and increase **Delay Time**, so that the tool waits more time before inspecting again. (**Default:** 3s, **Range:** 0-60s)

4. Hover over on **profile** object, select the **click** operation on the tooltip. The below test step gets added to the UFT Test and launch the login screen

	**AIUtil("profile").Click**
	
	The AI Record runs the default operation depending on the object type or runs the selected operation. It adds the step to the test only after the operation is successful.

5. After succesful completion of previous step, **AI Record** inspect and identify the objects on next screen i.e. AOS login screen 
	
	For input fields, search boxes, and combo boxes, the AI Record may prompt you to enter a value for the recorded step.
	
	You can see the recording progress, step code, recording result, as well as error messages from the toolbar.
	
	![step 2](/images/30_Create_UFT_AI_Based_Test/aos_login.png)

	Hover over on the **Username** and **Password** fields and select **type** operation to enter the input for respective fields
	
	**Note:** You can create your own user account on Advantage Online Shopping application or use the below user credentials
	
	**AIUtil("input", "Username").Type "aidemo"**
	
	**AIUtil("input", "Password").Type  "AIdemo1"**
	
	Hover over on the **SIGN IN** button and select **click** operation
	
	**AIUtil("button", "LOGIN").Click**
	
	The login to the AOS application should be successful
	
	**Tip:** If you face problems entering the Username input properly, pause recording enter the Username as specified above and then continue with the recording
	
	To pause the recording, click the **Pause** button  on the toolbar. You can then click the **Resume** button  later to resume the recording.
	
6. During recording, you can add a **checkpoint**. That means that you can check the existence or state of an object.

	To confirm succesful login, hover over on logged in Username i.e. text block **"aidemo"** and select **Add Checkpoint**, then select **"Exists"** radio button to add checkpoint step
	
	![step 3](/images/30_Create_UFT_AI_Based_Test/checkpoint.png)
	
	**AIUtil.FindTextBlock("aidemo").CheckExists True**
	
	**Note:**  

	The checkpoint for verifying existence applies to all visual elements and texts.
	
	The checkpoint for verifying states applies to only objects with an **On/Off** state, such as toggles, check boxes, and radio buttons.
	
	### To add a checkpoint

	Hover over a highlighted object you want the test to check.

	A tooltip displays, from which you can add a checkpoint for the object.

	Click **Add Checkpoint** on the tooltip.

	Select **Exist** or **Not Exist** for verify existence.

	Select True to check if the state is On or False to check if the state is Off.

	![step 3](/images/30_Create_UFT_AI_Based_Test/exists_notexists.png)

7. Hover over on the **Search** icon and select the **Search** operation, enter text “17t” as search keyword

	**AIUtil("search").Search "17t"**
	
	Keyword search should be succesful and display all the items that match the search criteria
	
	![step 3](/images/30_Create_UFT_AI_Based_Test/keyword_search.png)
	
8. Click on the **“HP ENVY – 17t touch”** Text block to select the item from the search results
	
	**AIUtil.FindTextBlock("HP ENVY - 17t Touch").Click**
	
9. Click on the **"ADD TO CART"** button to add the selected item to the shopping cart

	**AIUtil("button", "ADD TO CART").Click**
	
10. Hover over on the **"Shopping_Cart"** icon, select **"+Relation"** to add relation with **Help** icon next to it and then select **Click** operation
	
	**AIUtil("shopping_cart", micAnyText, micWithAnchorBelow, AIUtil("help")).Click**

	#### To add a relation:

	Hover over a highlighted object you want to identify.

	A tooltip displays, from which you can add a relation for the object.

	Click **"+Relation"** on the tooltip.

	Click on another object in proximity to add the relation.

	If the relation is successfully added, a blue dot appears next to the object you want to identify.

	To remove the added relation, hover over the object you want to identify again and click Remove Relation on the tooltip. The AI Record will validate the object and restore the relation in case that the object becomes invalid.

	**Note:**  You can select only available objects in proximity on the web page or application.
	
	You cannot add a relation if the object you selected has a circular relation with the object you want to identify. **Circular relation:** A series of objects defined by their proximity to one another, where the last object is defined by its proximity to the first.

11. Hover over on **Checkout** button and select **Click** operation

	**AIUtil("button", "CH ECKOUT ($849.99)").Click**




	