---
title: "Run/Debug UFT One AI-based Tests"
chapter: false
weight: 43
pre: "<b>4.3 </b>"
---

## UFT One Test Execution

To run the test that was created in the previous section, you can configure UFT One to launch a browser window and open the AOS application URL

You can configure the behavior of test recording and execution in the **Record and Run Settings**.

1. From the UFT One menu, Select **Record > Record and Run Settings**.

	![step 1](/images/40_Create_UFT_AI_Based_Test/RnR_toolbar.png)

2. Under the **Web** tab, select the following options to configure UFT One to open the AOS URL using Microsoft Internet Explorer for the run.

	Choose the radio button **Open the following when recording or running**:

	* **Use: Local Browser**

	* **URL: https://advantageonlineshopping.com**

	* **Browser: Microsoft Internet Explorer**

	![step 2](/images/40_Create_UFT_AI_Based_Test/RnR_settings.png)

	Click on **OK** 

3. You should also configure UFT One to save screenshots in the test results. 

	To enable screenshot capture in the test results, navigate to **Tools > Options > GUI Test > Screen Capture** and select

	* **Save still image captures to results: Always**

	![step 3](/images/40_Create_UFT_AI_Based_Test/screen_capture.PNG)

	Click on **OK** 
	
4. Click the **Run** button from UFT One's toolbar to execute the test

Alternatively the following lines can be added at the beginning of the test to open Microsoft Internet Explorer and navigate to the AOS URL

**SystemUtil.Run "C:\Program Files\internet explorer\iexplore.exe"**

**AIUtil.SetContext Browser("creationtime:=0")**

**Browser("creationtime:=0").Navigate "https://www.advantageonlineshopping.com"**

## Debug the UFT One Test

1. UFT One always runs a test from the first step, unless you specify otherwise.

	You can refer to the **GUI tests and components** section of the [UFT One online help](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Content/User_Guide/z_Ch_RunTestAndComps.htm#) page for different run methods for debugging

2. There may be a short delay before the objects the step acts on are visible on the screen during the execution.

	In such cases, adding **wait** statements for synchronization can help. The following example shows how to add a few seconds of delay while the page is loading, before the Username field appears.

	AIUtil.SetContext Browser("creationtime:=0")

	Browser("creationtime:=0").Navigate "https://advantageonlineshopping.com"

	**wait 3**

	AIUtil("profile").Click

	**wait 3**

	AIUtil("input", "Username").Type "aidemo"

3. If UFT One doesn't find an object specified in the AI step during the test execution, it scrolls through the page to find the object.

	**AIRunSettingsAutoScroll Object** controls automatic scrolling for AI identification in the current test run.

	By default, the automatic scrolling is on, and set to scroll down, up to **2** times.

	There is an object that contains the settings for the current test run. These settings enable you to modify test settings during the test run, overriding the global settings defined in **Tools > Options > GUI Testing > AI**.

	Refer to the [UFT One online help](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Subsystems/OMRHelp/Content/AI/AIPackageLib~AIRunSettings.html?Highlight=AIUtil) for complete details regarding **AIRunSettings Object**

4. If AI-based object identification is not working properly and needs to update an AI-based test step, refer to the [Test Objects Identification using AI Inspect](/40_create_uft_ai_based_test/5_ai_inspect.html) section for details.

5. For additional recommendations on writing AI-based tests, read the [Tips and tricks for AI-based testing](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Content/User_Guide/AI-based-testing-tips-and-tricks.htm) article on the UFT One online help.

