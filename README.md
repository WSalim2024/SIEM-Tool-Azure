<h1> SIEM-Tool-Azure </h1>
<br />
<h2> Steps to Set Up SIEM using Azure Sentinel </h2>
<br />
<h3>Azure Portal & Subscription</h3>
        <br/>
        <ul>
                <li>A.	Create an account on Azure Portal -- https://portal.azure.com/ which includes $200 worth of free credits - Note: You will need to enter a credit card, but you likely won't use all the credits for this lab.
                    <br><img width="700" alt="1" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/5eed9549-599a-4098-a4ac-ce7c53033e96"></li>
                <li>B.	Login to your account.<br></li>
                <li>C.	Signup for Trial subscription.</li>
                    <br><img width="957" alt="4" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/7e1e5078-1163-4c0a-8524-89a4318dd9b7"></li>
                <li>D.	Navigate to main Dashboard 
                    <br><img width="960" alt="5" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/af98fd3c-9584-4c37-add4-fee096e76219"></li>
        </ul>
<br />
<h3>Virtual Machine</h3>
<br/>
        <ul>
                <li>Go to [portal.azure.com](https://portal.azure.com) and search Virtual MAchines in the top search bar.<br>
                <img width="960" alt="6" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/0016a404-4c35-47d3-bd24-736ca7c71e56"></li>
                <li>Create a new virtual machine and in the basics tab under Resource Group click on <b>Create new</b> to create a new resource group. We will add everything                         to this resource group<br>
                <img width="960" alt="7" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/d7f58bee-91d5-4842-b826-0da68d6ae418"></li>
                <li>Create a new resource group for the lab (e.g., "SIEMLab").<br>
                <img width="959" alt="8" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/53db8c1d-6cd9-42a7-860d-f8a29a6f76df"></li>
                <li>Name the VM (e.g., "SIEMVM" or "SIEM-vm").<br></li>
                <li>Set the region (e.g., "Europe France Central"). Use the regio,n closest to you in your case.<br></li>
                <li>Use the Windows 10 Pro VM image<br></li>
                <img width="960" alt="10" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/1c25fbcb-4b4e-4474-9096-8cddb407fb32"></li>
                <li>For the size option, I would recommend using 2 vcpus, 16 Gig memory for a smooth experience.<br></li>
                <li>Create a username and password for the VM.<br>
                <img width="960" alt="11" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/026b5ced-3042-43f7-b56d-cb644a539e70"></li>
                <li>Make sure the options are selected as shown below. Public Inbound ports to "Allow Selected Ports" and Select "Select inboud ports" to RDP 3389(can be                         different in your case. After it click "Next"<br>
                <img width="959" alt="12" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/49d99011-8d9d-4282-b301-668de149c25e"></li>
                <li>Do not change any setting in the Disks section and click "Next" to continue.<br>
                <img width="955" alt="13" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/c63564c0-25c6-4b8c-9e49-6b3dc20e78ae"></li>
                <li>Now in the "Networking" tab, make sure it is like below:<br>
                <img width="960" alt="14" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/34fb3af8-e157-4129-90f8-a51ee160d2b5">
                <img width="953" alt="15" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/ea7f0e63-67f2-4890-940b-5a78dd0b3dcc"></li>
                <li>In the "Networking" tab where it says, highlighted in screenshot, "Configure network security group", right next to it click on "Create new" Configure                         the network security group:<br>
                <img width="958" alt="16" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/f93c92c8-77dd-45cd-95ad-3aa663869100"></li>
                <li>Remove all default rules both inbound and outbound. and should look like the second screen shot below<br>
                <img width="960" alt="17" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/d07c737d-2b9e-4054-9059-5fe34d1d6fef">
                <img width="960" alt="18" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/f786c466-ce48-4fdf-aaf9-9dddf07c7ed4"></li>
                <li>Create a new security group allowing all inbound traffic:<br>
                <img width="955" alt="19" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/5dd4de98-3537-4b0c-997e-401c583b1098"></li>
                <li>Scroll down in "Action" select "Allow", set "Priority" to 100 and in the "Name" you can put anything that defines this rule. Click on "Add" to add the                         rule and "Ok" to create the new security group. Before clicking ok name the security group, I named mine "SIEM-VM-nsg".<br>
                <img width="960" alt="20" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/a66133bb-b327-4728-ab6d-f8a71d5f79f9"></li>
                <li>Now it zill return you to the "Networking" page and the new security group we just created will be selected on the "Configure network security group"                         section.<br>
                <img width="960" alt="21" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/e953e6c8-d134-4b07-b021-64f817a38e8f">
                <img width="960" alt="22" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/01b16719-aef5-4f14-b755-f507c417f4d9"></li>
                <li>Review and create the VM.<br>
                <img width="960" alt="24" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/b698512a-31cb-4330-bf44-b1739be92875">
                <img width="960" alt="25" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/8a5578ae-14a5-46bc-b736-6255d66e69b1">
                <img width="958" alt="26" src="https://github.com/WSalim2024/SIEM-Tool-Azure/assets/170832525/81389e65-d7f6-4db8-ac31-9a75bf4d31d4"></li>
        </ul>
                
