![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/6f0710e2-3830-4451-8883-05bf874d7332)


<h1>Network-File-Shares-and-Permissions</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Domain Controller/Client Machine)
- Remote Desktop
- Shared Network Files

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

</p>
<p>
In this lab we will be setting up shared network files & permissions. We will create folders in the DC-1 VM and share them on the network certain files will have certain permissions. Only designated people will be able to view certain files. Lets get started. First go to the c:/ drive on the DC-1 machine and create 4 folders. "read-access" "read/write-access" "no-access" and "accounting".
</p>
<br />

![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/4e50919a-0589-4d5f-a2be-83bfbbc68233)

<p>
After the folders have been created what you want to do is share them on the network so that the client-1 machine can view them. We can also set the permissions of the folders in DC-1. Set the folders to the appropriate permissions. "read-access" should be read only for domain users, "read/write access" shuld have read/write permissions for domain users. Lastly "no-access" should have read/write permissions for domain admins only.
</p>
<br />

![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/c0fecba3-8a47-4d6a-96b8-c0aabcff1f00)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/06053cd8-b221-4f5d-8a0a-9c079a9ff471)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/63ae4e72-16c9-4827-82b4-3988cf368a5e)


If we login to the client machine with a normal user account we can test out the shared files we just created. As you can see the permissions that we set are working properly.
</p>
<br />
<p>
<img src="https://i.imgur.com/CGQ8yaO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/f9TldBO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
</p>
Go back to the DC-1 VM. In AD create a security group called "Accountants" the users assigned to this security group will be the only ones allowed to view the "Accountants" folder. We have to share the "Accountants" folder just like we did in the last section, this we will be sharing it to only the accountants group. Normal users will not have access to this folder. If we wanted to give a normal user access to the accounting folder they would have to be a part of the "Accountants" security group.
</p>
<br />
<p>
<img src="https://i.imgur.com/QADy92Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/BUm3L2Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<img src="https://i.imgur.com/fH8fU7b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
