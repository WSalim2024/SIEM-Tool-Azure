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
                <li>Create a new resource group for the lab (e.g., "honeypot lab").<br></li>
                <li>Name the VM (e.g., "honeypot" or "honeypot-vm").<br></li>
                <li>Set the region (e.g., "West US 2").<br></li>
                <li>Use the default VM image and size.<br></li>
                <li>Create a username and password for the VM.<br></li>
                <li>Configure the network security group:<br></li>
                <li>Go to the networking tab and set the network security group to advanced.<br></li>
                <li>Create a new security group allowing all inbound traffic:<br></li>
                <li>Remove default rules.<br></li>
                <li>Create a new inbound rule allowing all traffic (destination port: *, protocol: *, action: allow, priority: 100).<br></li>
                <li>Review and create the VM.<br></li>
        </ul>
                
