<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="696" height="344" alt="image" src="https://github.com/user-attachments/assets/29798ab4-ab6b-47c0-aed4-e3c820b04d97" />

</p>
<p>
<b>1) </b>Create a Resource Group.
</p>
<br />

<p>
<img width="702" height="642" alt="image" src="https://github.com/user-attachments/assets/070a01cd-e7ca-4909-9bc4-f34e6d99fc2c" />
</p>
<p>
Create a Virtual Network and Subnet.
</p>
<br />

<p>
<img width="832" height="563" alt="image" src="https://github.com/user-attachments/assets/a768d60b-6685-49d4-a1e4-2983fb747dc9" />
<img width="519" height="330" alt="image" src="https://github.com/user-attachments/assets/b58fb22f-8d2a-46f9-b8a5-fe3bd3a0f1f5" />
<img width="565" height="427" alt="image" src="https://github.com/user-attachments/assets/f9ab54d0-76c1-41c7-99f1-f1b02c61556f" />

</p>
<p>Create the Domain Controller VM (Windows Server 2022) named “DC-1”</p>
<br />

<p>
<img width="842" height="474" alt="image" src="https://github.com/user-attachments/assets/4e52fc1b-eb9e-4df5-bb19-a3532b898cbf" />
<img width="912" height="635" alt="image" src="https://github.com/user-attachments/assets/5f19072d-d003-4a39-977c-d9e9617c90fc" />

</p>
<p>After VM is created, set Domain Controller’s NIC Private IP address to be static.</p>
<br />

<p>
<img width="1279" height="769" alt="image" src="https://github.com/user-attachments/assets/9d52b2e3-9f58-4a50-be7d-8db6eb164449" />
<img width="342" height="247" alt="image" src="https://github.com/user-attachments/assets/4d2cc561-768d-42af-8892-1b1c2f508bb1" />
<img width="742" height="549" alt="image" src="https://github.com/user-attachments/assets/5265fbc1-e86a-405b-9e1a-a99afb087001" />
<img width="290" height="322" alt="image" src="https://github.com/user-attachments/assets/92eddf93-6244-4ed9-b5f0-1ec2f42f9d80" />


</p>
<p>Log into the VM and disable the Windows Firewall (for testing connectivity)</p>
<br />

<p>
<img width="579" height="614" alt="image" src="https://github.com/user-attachments/assets/56e1aec9-49b3-41cf-980e-f58725143101" />
<img width="566" height="347" alt="image" src="https://github.com/user-attachments/assets/de6287a3-eca8-4acb-b4b8-e55e8ce668c1" />
<img width="583" height="461" alt="image" src="https://github.com/user-attachments/assets/9636245f-f9b3-4843-a7ba-855c153e60d4" />

</p>
<p>Create the Client VM (Windows 10) named “Client-1”</p>
<br />

<p>
<img width="837" height="445" alt="image" src="https://github.com/user-attachments/assets/0ac4409a-f898-4327-bfe1-f45702a1e22a" />
<img width="1106" height="445" alt="image" src="https://github.com/user-attachments/assets/87c52212-ccb3-45d2-914d-7fb28ec3225a" />


</p>
<p>After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address.</p>
<br />

<p>
<img width="1102" height="308" alt="image" src="https://github.com/user-attachments/assets/a510beb0-10fe-40d9-a2d7-8e6b5a083aea" />

</p>
<p>From the Azure Portal, restart Client-1.</p>
<br />

<p>
<img width="1102" height="308" alt="image" src="https://github.com/user-attachments/assets/a510beb0-10fe-40d9-a2d7-8e6b5a083aea" />

</p>
<p>From the Azure Portal, restart Client-1.</p>
<br />

<p>
<img width="904" height="374" alt="image" src="https://github.com/user-attachments/assets/abe2833c-4d2b-4fce-bd5f-97be0658b165" />
<img width="1272" height="682" alt="image" src="https://github.com/user-attachments/assets/1e7d3275-fde1-4ab7-98ca-e87ce367805f" />
</p>
<p>Login to Client-1</p>
<p>Attempt to ping DC-1’s private IP address</p>
<p>-Ensure the ping succeeded</p>
<p>From Client-1, open PowerShell and run ipconfig /all</p>
<p>The output for the DNS settings should show DC-1’s private IP Address</p>
<br />

<p>
<img width="808" height="531" alt="image" src="https://github.com/user-attachments/assets/50724b3d-4864-47b6-8afc-ab4bbb80f35f" />
<img width="559" height="392" alt="image" src="https://github.com/user-attachments/assets/5cd1560d-6ee2-486b-8087-3f5058aaac76" />
<img width="556" height="397" alt="image" src="https://github.com/user-attachments/assets/fd8427b4-420f-460d-877d-607df82397bb" />

</p>
<p>Install Active Directory</p>
<p>Login to DC-1 and install Active Directory Domain Services
</p>

<br />

<p>
<img width="1275" height="676" alt="image" src="https://github.com/user-attachments/assets/63a0ca77-bd5d-44b6-902a-a3f9ef711bad" />
<img width="540" height="391" alt="image" src="https://github.com/user-attachments/assets/d9daa683-995f-4698-a13e-f3cab043d3de" />
<img width="533" height="394" alt="image" src="https://github.com/user-attachments/assets/96f0b25d-0054-44ac-b1d1-2c91934e616d" />


</p>
<p>Promote as a DC: Setup a new forest as mydomain.com (can be anything, just remember what it is)</p>
<p>-Restart and then log back into DC-1 as user: mydomain.com\labuser</p>
</p>

<br />

<p>
<img width="558" height="414" alt="image" src="https://github.com/user-attachments/assets/8a7ce7ab-291e-4102-b1cc-e02951f42cc5" />
<img width="1363" height="707" alt="image" src="https://github.com/user-attachments/assets/617b7a6d-26ef-4027-947d-d49b1209a6cc" />
<img width="597" height="514" alt="image" src="https://github.com/user-attachments/assets/10c82e51-9c79-4977-8532-ec1af0f2e0d2" />
<img width="617" height="522" alt="image" src="https://github.com/user-attachments/assets/1f40d079-cd11-4f2d-972b-64d569e6a36d" />

</p>
<p>Create a Domain Admin user within the domain</p>
<p>-In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”</p>
<p>-Create a new OU named “_ADMINS”</p>
</p>

<br />

<p>
<img width="1350" height="752" alt="image" src="https://github.com/user-attachments/assets/7611dc05-ec7c-4cf1-a128-092d91c472ab" />
<img width="600" height="513" alt="image" src="https://github.com/user-attachments/assets/f4a6be60-9c7d-4045-aa2b-bdd15de4984b" />
<img width="1268" height="680" alt="image" src="https://github.com/user-attachments/assets/8e5f5f13-0ae9-4660-8b0d-0cc4e76def16" />
<img width="1162" height="765" alt="image" src="https://github.com/user-attachments/assets/d83016d7-a40d-4806-91f2-0eb5526d31a6" />
<img width="444" height="249" alt="image" src="https://github.com/user-attachments/assets/68c99b75-cf76-49d8-bb7b-d9cad232c08d" />


</p>
<p>Create a new employee named “Jane Doe” with the username of “jane_admin” / Cyberlab123!</p>
<p>Add jane_admin to the “Domain Admins” Security Group</p>
<p>Log out / close the connection to DC-1 and log back in as “mydomain.com\jane_admin”.
User jane_admin as your admin account from now on</p>
</p>

<br />

<p>
<img width="823" height="625" alt="image" src="https://github.com/user-attachments/assets/e9974909-de03-40b5-ba67-84bf6391a181" />
<img width="384" height="392" alt="image" src="https://github.com/user-attachments/assets/56526096-4fc2-4864-854a-d68c3279eea1" />
<img width="340" height="225" alt="image" src="https://github.com/user-attachments/assets/85d672ce-7736-46ff-a198-fa4401106441" />


</p>
<p>Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)</p>


<br />

<p>
<img width="1102" height="616" alt="image" src="https://github.com/user-attachments/assets/4f2fb7d9-403b-488c-8f3b-1cbb755555bd" />


</p>
<p>Login to the Domain Controller and verify Client-1 shows up in ADUC</p>

<br />

<p>
<img width="936" height="498" alt="image" src="https://github.com/user-attachments/assets/7e87bea4-13ad-4391-ac4c-12e5e340bef7" />

</p>
<p>Create a new OU named “_CLIENTS” and drag Client-1 into there</p>

<br />

<p>
<img width="846" height="650" alt="image" src="https://github.com/user-attachments/assets/060448a9-a1ef-4b04-8237-792de85b0fe0" />
<img width="395" height="248" alt="image" src="https://github.com/user-attachments/assets/2288bd67-109c-480f-846b-ae00ab330b0f" />


</p>
<p>Setup Remote Desktop for non-administrative users on Client-1</p>
<p>-Log into Client-1 as mydomain.com\jane_admin</p>
<p>-Open system properties</p>
<p>-Click “Remote Desktop”</p>
<p>-Allow “domain users” access to remote desktop</p>
<p>You can now log into Client-1 as a normal, non-administrative user now</p>
<br />


<p>
<img width="624" height="481" alt="image" src="https://github.com/user-attachments/assets/2597259b-a52d-43ad-b82f-42fa9bd71bcd" />
<img width="1084" height="729" alt="image" src="https://github.com/user-attachments/assets/1af81c68-88ff-40af-88c8-3b392018de50" />
<img width="1292" height="453" alt="image" src="https://github.com/user-attachments/assets/39964fd4-aa7d-4033-bc51-7aaee7f1ece0" />
<img width="999" height="744" alt="image" src="https://github.com/user-attachments/assets/e36c688e-9e8a-46ad-9df0-62489b550d71" />
<img width="1272" height="655" alt="image" src="https://github.com/user-attachments/assets/0ce80d0e-cff2-4f76-ac34-7d3993097db7" />


</p>
<p>Create a bunch of additional users and attempt to log into client-1 with one of the users</p>
<p>-Login to DC-1 as jane_admin</p>
<p>-Open PowerShell_ise as an administrator</p>
<p>-Create a new File and paste the contents of the script: https://github.com/joshmadakor1/AD_PS/blob/master/Generate-Names-Create-Users.ps1 into it</p>
<p>-Run the script and observe the accounts being created</p>
<p>-When finished, open ADUC and observe the accounts in the appropriate OU　(_EMPLOYEES)</p>
<p>-Attempt to log into Client-1 with one of the accounts (take note of the password in the script: "Password1" and username style: mydomain.com\"random name")</p>
<br />

<p>
<img width="324" height="174" alt="image" src="https://github.com/user-attachments/assets/67df0a4b-ec08-4379-949d-91f7bee39bf8" />
<img width="827" height="552" alt="image" src="https://github.com/user-attachments/assets/ed6113d8-2eb7-4f31-b3e6-b4d322a83564" />
<img width="1064" height="417" alt="image" src="https://github.com/user-attachments/assets/f88e3c71-b7c2-497d-9220-54c99d007f56" />
<img width="298" height="357" alt="image" src="https://github.com/user-attachments/assets/3bc3d36d-bb11-437d-885a-e4bfb906e34e" />
<img width="303" height="355" alt="image" src="https://github.com/user-attachments/assets/8e79146a-a984-4466-9b59-65ebd9410c9b" />
<img width="684" height="359" alt="image" src="https://github.com/user-attachments/assets/66a7db80-e4a0-4e06-ba6c-ead1d48bdebd" />


</p>
<p>Configuring an account lockout policy in Active Directory using Group Policy involves defining settings that control when an account is locked after multiple failed login attempts, how long the account remains locked, and how the lockout counter is reset. Here’s a step-by-step guide on how to do this:
</p>
<p>-Log in to a machine with Group Policy Management Console installed (typically, a Domain Controller). </p>
<p>-Click Start, and type gpmc.msc in the search box, then press Enter. This opens the Group Policy Management Console.</p>
<p>-In the GPMC, navigate to the Group Policy Objects section.</p>
<p>-Right-click Group Policy Objects and select New to create a new GPO, or right-click an existing GPO and select Edit to modify it.</p>
<p>-In the Group Policy Management Editor, expand the following:
Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy.</p>
<p>-Configure Account Lockout Policy Settings</p>
<p>-Update Group Policy</p>

<br />

<p>
<img width="183" height="218" alt="image" src="https://github.com/user-attachments/assets/4f3a2179-a467-4a4a-8195-53a1d7bfcf74" />
<img width="1056" height="526" alt="image" src="https://github.com/user-attachments/assets/7b610a6f-ed11-44ae-8126-3adee866000d" />
<img width="360" height="357" alt="image" src="https://github.com/user-attachments/assets/3ae7fec9-1d12-421d-90a3-27fb221dfdd7" />


</p>
<p>Dealing with Account Lockouts</p>
<p>-Get logged into dc-1.</p>
<p>-Pick a random user account you created previously.</p>
<p>-Attempt to log in with it 5 times with a bad password.</p>
<p>-Observe that the account has been locked out within Active Directory.</p>
<p>-Unlock the account.</p>
<p>-Reset the password.</p>
<p>-Attempt to log in with it.</p>

<br />


<p>
<img width="591" height="458" alt="image" src="https://github.com/user-attachments/assets/ccb0553a-ad8c-4f71-a419-f6b44d8c25c4" />
<img width="185" height="181" alt="image" src="https://github.com/user-attachments/assets/a2391d8b-a262-4f0e-a20f-cee2285cbc98" />
<img width="468" height="407" alt="image" src="https://github.com/user-attachments/assets/b721a674-236f-476e-9039-fd642dbfa8c2" />



</p>
<p>Enabling and Disabling Accounts</p>
<p>-Disable the same account in Active Directory.</p>
<p>-Attempt to login with it, observe the error message.</p>
<p>-Re-enable the account and attempt to login with it.</p>


<br />


<p>
<img width="552" height="399" alt="image" src="https://github.com/user-attachments/assets/c654e517-655b-417e-ae68-3fffb10def74" />
<img width="1119" height="665" alt="image" src="https://github.com/user-attachments/assets/d8a5e74f-5b31-4734-9396-fcdbc2fee19d" />
<img width="1146" height="585" alt="image" src="https://github.com/user-attachments/assets/028973bd-aafd-49f5-85f1-486ec32f0acf" />


</p>
<p>Observing Logs</p>
<p>-Observe the logs in the Domain Controller.</p>
<p>-Observe the logs on the client Machine.</p>


<br />
