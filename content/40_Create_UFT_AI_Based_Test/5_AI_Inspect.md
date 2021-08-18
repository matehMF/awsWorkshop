---
title: "Test Objects Identification using AI Inspect"
chapter: false
weight: 45
pre: "<b>4.5 </b>"
---

## UFT One AI Inspect overview

Use **AI Inspection** to identify objects in your application under test (AUT), that you can use in your test steps.

To identify all objects on the web page, open the **AI Identification View window** to inspect your application and detect all AI objects in it.

To open the window, do one of the following:

1. Click the **AI Identification** toolbar button.

	In the **Object Spy** or **Object Identification Center**, click **INSPECT**.

	**Tip:** This button is available when the **AI Auto Inspection** option is enabled.

2. Click the **AI Identification** toolbar button, click on the web page on which you want to identify AI-based test objects

	The AI Identification View displays an image of the application, highlighting all of the detected objects.

	You can decide whether to show **Visual Element** or **Text**, to see either the objects that UFT One detected visually, or areas of text in the application.

## Identify Test Objects using UFT One AI Inspect

In the following steps, we will add an AI-based test step using **AI Identification** to the existing AI-based test that was created using **AI Recording** earlier.

1. Navigate to the **"HP ENVY - 17T TOUCH LAPTOP"** web page on AOS application as shown in the screenshot in step #2 below

2. Click the **AI Identification** toolbar button, and click on the **"HP ENVY - 17T TOUCH LAPTOP"** page that was opened in the previous step

	The **AI Identification View** displays an image of the application, and highlights all of the detected **Visual Element** objects on the page.

	![step 1](/images/40_Create_UFT_AI_Based_Test/ai_inspect_visual_element.PNG)

	Drag and drop the visual element **"+"** button object to the test, just before the **Add to Cart** step, to select an additional quantity of the item chosen.

	The updated test steps should look as follows:

	.....................................................

	**AIUtil("plus").Click**

	**AIUtil("button", "ADD TO CART").Click**

	.....................................................

Similarly you can use the **AI Identification** to update any existing AI-based test step in your test.

