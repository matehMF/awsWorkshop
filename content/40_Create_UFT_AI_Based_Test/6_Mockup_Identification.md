---
title: "Test Objects Identification using Application Mockups"
chapter: false
weight: 46
pre: "<b>4.6 </b>"
---

## AI Mockup Identification overview

**Supported on UFT One versions 15.0.2 and later**

Use **AI Mockup Identification** to inspect application mockups and identify objects you could use in your test. In this way, you can prepare your test much earlier and design your test even before your application is fully developed.

#### Prerequisites

**AI Mockup Identification** requires no web or mobile application. Instead, you need to load images in **.jpg, .jpeg, or .png** format from a local folder.

Inspect application mockups

1. In the UFT One toolbar, click the down arrow near the **AI Identification** button  and select the **AI Mockup Identification**.

	![step 1](/images/40_Create_UFT_AI_Based_Test/ai_mockup.png)

	In the dialog box that opens, select a folder containing images, select Web or Mobile as the AI identification context, and click Open.

2. The **AI Mockup Identification View** loads all of the images in the folder by file name and creates an image gallery.

3. The **AI Mockup Identification View** inspects the image that appears first in the file name order and highlights all identified visual elements by default.

4. To manage images in the folder, edit settings in the image gallery:

	Select File Name or Modified Time to sort the images by file name or modified time.

	Click Refresh to refresh the images if the images are changed.

	Click Choose different to select a different folder of images to inspect.

	To achieve optimal identification, edit settings on the inspected page:

	Select **Visual Element** or **Text** to show either the objects that UFT One identified visually or areas of text.

	Select **Web** or **Mobile** to change your AI identification context again.

## Create AI-based test using Mockup identification

Thanks to the Computer Vision, you can **start test Design without application**. You can easily Build an AI-based test script based on application Mockup

Now let's create an AI based test script for AOS application login using application Mockup screens

As a prerequisite, store AOS application images in **.jpg, .jpeg, or .png** format in a local folder path: "C:\Users\demo\Documents\Mockups".

**Note:** You can right click on the **Mockup images** of AOS application in the below steps to download and save them to the local folder

1. In the UFT One toolbar, click the down arrow near the **AI Identification** button  and select the **AI Mockup Identification**.

2. Select a folder which contains the Mockup images of AOS application and click Open after selecting **AI identification context** as **Web**

	**Select the AI identification context: Web**

	![step 2](/images/40_Create_UFT_AI_Based_Test/mockup_images.PNG)

3. Choose the AOS home Mockup image, the **AI Mockup Identification View** inspects the **Visual Elements** from the image by default

	![step 3](/images/40_Create_UFT_AI_Based_Test/mockup_identification1.PNG)

	Drag and drop the **Profile** visual element from the Mockup identification to your test step

	**AIUtil("profile").Click**

4. Click on the second picture in the **image gallery**

	**AI Mockup Identification View** inspects the **Visual Elements** from the image as below

	![step 4](/images/40_Create_UFT_AI_Based_Test/mockup_identification2.PNG)

	Drag and drop the **Username, Password** input fields and **LOGIN** visual elements from the Mockup identification to your test step

	Enter the input values for the **Username and Password** fields

	**AIUtil("input", "Username").Type "aidemo"**

	**AIUtil("input", "Password").Type "AIdemo1"**

	**AIUtil("button", "LOGIN").Click**
