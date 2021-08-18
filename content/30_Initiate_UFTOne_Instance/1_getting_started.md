---
title: "Creating Your UFT One Environment"
chapter: false
weight: 31
pre: "<b>3.1 </b>"
---

## Starting the AWS EC2 UFT One Instance

In this section we will explain how to set up your UFT One environment from the AWS Marketplace image. UFT One is available from the [AWS Marketplace] (https://aws.amazon.com/marketplace/pp/prodview-q2d32aqrwglr4).


**UFT One is a desktop application, and should be accesssed via Remote Desktop (RDP) to the Windows server.**

**:white_check_mark: Step-by-step Instructions**

1. From the AWS Management Console, select **Services**, then select **EC2** or **Search** for it.

![Step 1](/images/30_Initiate_UFTOne_Instance/search-ec2.png)

2. Select **AMIs**.

![Step 2](/images/30_Initiate_UFTOne_Instance/Ec2_AMI.png)

3. Change to **Public images**.

![Step 3](/images/30_Initiate_UFTOne_Instance/ami_public.png)

4. Add filter **"UFT"** and press Enter.

![Step 3](/images/30_Initiate_UFTOne_Instance/uft_ami_details.png)

5. Select the **UFT 15_02 update...** from Marketplace and in **Actions** select **Launch**.

![Step 3](/images/30_Initiate_UFTOne_Instance/ami_launch.png)