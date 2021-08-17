---
title: "Run/Debug UFT One AI-based Tests"
chapter: false
weight: 43
pre: "<b>4.3 </b>"
---

## UFT Test Execution

To run the test that has been created in the previous section, you can configure UFT One to launch a browser window and open the AOS application URL

You can define record and run settings using the UFT **Record and Run Settings** option

1. From the UFT One toolbar, Select **Record > Record and Run Settings**.

	![step 1](/images/40_Create_UFT_AI_Based_Test/RnR_toolbar.png)

2. Under **Web** tab, select the below options to set the UFT One open AOS url using Internet Explorer during run

	Tick the radio button **Select the following when recording or running**

	**Use: Local Browser**

	**URL: https://advantageonlineshopping.com**

	**Browser: Microsoft Internet Explorer**

	![step 2](/images/40_Create_UFT_AI_Based_Test/RnR_settings.png)

3. Click on **Apply** and **OK** buttons

4. Also enable "Save still image captures to results" with "Always" option in order to view the screenshots in the test results

	To enable screenshots capture in results navigate to **Tools > Options > GUI Test > Screen Capture** and select

	**"Save still image captures to results": "Always"**

	![step 3](/images/40_Create_UFT_AI_Based_Test/screen_capture.PNG)

5. Click on **Run** button from the UFT toolbar to execute the test

Alternatively the below lines of code can be added at the beginning of the test to open Microsoft Internet Explorer and navigate to AOS URL

**SystemUtil.Run "C:\Program Files\internet explorer\iexplore.exe"**

**AIUtil.SetContext Browser("creationtime:=0")**

**Browser("creationtime:=0").Navigate "https://www.advantageonlineshopping.com"**

## Debug UFT AI Test

1. UFT One always runs a test from the first step, unless you specify otherwise.

	You can refer the **GUI tests and components** section of the [ADM Help](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Content/User_Guide/z_Ch_RunTestAndComps.htm#) page for different run methods for debugging

2. Please notice that due to the DOM components/Page loading delay, the expected objects may not be visible on the screen for an UFT AI step during the execution.

	In such cases, adding **wait** statements for synchronization would help. In the below example adding few seconds of delay while the page is loading and before Username field appears.

	AIUtil.SetContext Browser("creationtime:=0")

	Browser("creationtime:=0").Navigate "https://advantageonlineshopping.com"

	**wait 3**

	AIUtil("profile").Click

	**wait 3**

	AIUtil("input", "Username").Type "aidemo"

3. When UFT do not find an object specified in the AI step during the test execution, it tries to scroll through to find the the object.

	**AIRunSettingsAutoScroll Object** controls automatic scrolling for AI identification in the current test run.

	By default, the automatic scrolling is on, and set to scroll down, up to **2** times.

	An object containing the settings for the current test run. These settings enable you to modify test settings during the test run, overriding the global settings defined in **Tools > Options > GUI Testing > AI.**

	Refer the [ADM Help](https://admhelp.microfocus.com/uft/en/15.0-15.0.2/UFT_Help/Subsystems/OMRHelp/Content/AI/AIPackageLib~AIRunSettings.html?Highlight=AIUtil) for complete details regarding **AIRunSettings Object**

4. If AI based object identification not working properly and needs to update a AI based test step, refer the **Identify Test Objects by AI Inspect** for the details

