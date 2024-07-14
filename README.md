![image](https://github.com/user-attachments/assets/e1ca559c-2919-4e84-be36-97a0d9a12f7b)
</p>

<h1>Sharing resources over the network</h1>
Tutorial for sharing resources over a network<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Users and Computers

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Active Subscription (Creation of Reasearch Group, VMs, Virtual Networks, Subnets)
- Active Directory running in Azure on a virtual machine (DC1)
- Client machine running in Azure on a VM (Client1) and joined to the domain

<h2>Steps: 1 - 10</h2>

![image](https://github.com/user-attachments/assets/504e4a22-51c3-41a7-a06f-54773e4da692)
<p>
Step 1: Log into Domain Controller (ex: DC1) as domain admin account (ex: jerry_admin) -> Minimize
</p>
<br />

![image](https://github.com/user-attachments/assets/3205ce92-c457-48f2-871e-fd3fe49aa94b)
<p>
Step 2: Log into Client1 as a normal user (ex: cutoco.kupe)
</p>
<br />

![image](https://github.com/user-attachments/assets/35ccb5e8-be2b-45ca-b771-842fd7ac4ecb)
<p>
Step 3: On DC1 -> Navigate to C:\  drive -> create 4 folders: "read-access", "write-access", "no-access", "accounting"
</p>
<br />

![image](https://github.com/user-attachments/assets/9e91674b-ea2c-4a51-a8f5-b94ee29c81d2)
<p>
Step 4: In the "read-access" folder, create a text file(ex: read only!) with text inside that says "hello" 
</p>
<br />

![image](https://github.com/user-attachments/assets/91390ef0-a5c5-4062-ab9b-9a905c6c79fb)
<p>
Step 5: Set permissions for Folder: "read-access", Group: "Domain Users", Permission: "Read"
</p>
<p>
read-access -> Properties -> Sharing -> Share... -> enter "domain users" -> Add -> Share -> Done
</p>

![image](https://github.com/user-attachments/assets/98a59f9d-f676-4894-8eea-cedc40001105)
<p>
Step 6: Set permissions for Folder: "write-access", Group: "Domain Users", Permissions: "Read/Write"
</p>
<p>
write-access -> Properties -> Sharing -> Share... -> enter "domain users" -> Add -> Permission Level: Read/Write -> Share -> Done
</p>

![image](https://github.com/user-attachments/assets/98a834c4-7493-4a47-abb7-718ee4a6740b)
<p>
Step 7: Set permissions for Folder: "no-access", Group: "Domain Admins", Permissions: "Read/Write"
</p>
<p>
no-access -> Properties -> Sharing -> Share... -> enter "domain admins" -> Add -> Permission Level: Read/Write -> Share -> Done
</p>

![image](https://github.com/user-attachments/assets/10336e74-270e-4420-a431-8b26a5a80bdd)
<p>
Step 8: On Client1(ex: cutoco.kupe), navigate to the shared folder \\dc1
</p>
<br />

![image](https://github.com/user-attachments/assets/23ba2e16-4f45-4496-bc57-c899c595ba3f)
<p>
Step 9: Attempting to access the no-access folder should show an error message because cutoco.kupe is NOT an admin.
</p>
<p>
  
![image](https://github.com/user-attachments/assets/234d0558-afbc-4444-a942-700698d95fa2)
<p>
Step 10: Attempting to create anything in the read-access folder should show a message of denied access. However you are allowed to open the file and read it(ex: hello).
</p>

![image](https://github.com/user-attachments/assets/c602d3b4-03dd-4c85-8cfd-bb41d40f56b8)
<p>
Step 11: Attempting to create anything in the write-acesss folder(ex:new file!) should work properly
</p>
<br />
