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

![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/51371298-f124-4a3c-a621-f192c8affbab)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/50dcb472-6926-4dd3-87be-cbd34b717928)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/4ea3bdf5-947d-47c1-af0a-61a0b59b8420)


</p>
Go back to the DC-1 VM. In AD create a security group called "Accountants" the users assigned to this security group will be the only ones allowed to view the "Accountants" folder. We have to share the "Accountants" folder just like we did in the last section, this we will be sharing it to only the accountants group. Normal users will not have access to this folder. If we wanted to give a normal user access to the accounting folder they would have to be a part of the "Accountants" security group.
</p>
<br />
<p>

![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/6135de66-dc8f-4a9c-a9dc-08281f5b5a78)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/f32b2ab5-e9bc-4e41-b786-c8a08bb0420e)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/e7688ed1-6459-4191-91d3-910fff184186)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/38930871-d5db-4479-b7d3-0e62a37f7ad3)
![image](https://github.com/mathew-perez/Network-File-Shares-and-Permissions/assets/144407220/a920e50d-9c2e-4d13-9f25-a2b8ff5f21e9)

Hopefully this lab helped you build an intuition regarding network file shares and permissions.

