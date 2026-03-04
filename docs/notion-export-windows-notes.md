# Windows

### Administrating Local User Accounts

![image.png](image.png)

This allows us to manage both other user accounts as well as our own

We can also use run → lusrmgr.msc to launch the Local Users and Groups GUI

![image.png](image%201.png)

![image.png](image%202.png)

Local admin has total access to the computer such as all files, the ability to add apps and hardware drivers, admin accounts also have the ability  to manage user accounts on the local machine. 

![image.png](image%203.png)

By adding someone in the Admin group it allows that individual's account to gain the abilities the local admin has. This is great when you want to give certain permission to a user on a specific  machine the ability to have full access. 

### Adding a local user

Right click → New User 

![image.png](image%204.png)

![image.png](image%205.png)

![image.png](image%206.png)

By opening the new user the Admin can add the user to the Administrators group. 

![image.png](image%207.png)

By right clicking on the user the local admin can set the users password, rename the account, or delete it all together.

## Ticket

Ticket #44521 : Add user to Windows computer

Assigned: Admin                                   Status: Open

Comments: Hello, can you please add a local user James to the Windows Computer. Please created a account so that the user will have to change their password the first time they log in. In addition, please make the user an local administrator. 

![image.png](image%208.png)

The first step is to log in to thew work station as Admin and open the Local User and Groups GUI. There the new user can be added with the required password reset option added. 

![image.png](image%209.png)

![image.png](image%2010.png)

Using the Properties menu James can be removed from the user group and added to the Administrators group. 

## Local File Permissions

![image.png](image%2011.png)

To start we create a new file in the Admin account by pressing the top left +New button and naming the folder in this case test folder.

![image.png](image%2012.png)

When the admin user created a file this way all other users are able to read and modify the content. 

![image.png](image%2013.png)

First thing we have to do is remove the inherited permissions to effectively change access. This is because files with inherited permissions get them from their parent. meaning that what ever the original permissions are they would override any permissions made manually. 

![image.png](image%2014.png)

Now that the file permission where changed to only the Admin, the user can no longer access the file. 

![image.png](image%2015.png)

And if the file is needed to be access by the user, the admin can come and access the file for the user. 

## Windows Updates

![image.png](image%2016.png)

Windows checks for updates continuously and Microsoft releases them the second Tuesday of every month unless there is an emergency push due to an security issues such as a zero-day.  The Cumulative update preview is used for organization to test the update in a controlled environment to ensure it will not cause issues to the production machines. 

![image.png](image%2017.png)

![image.png](image%2018.png)

If the a update caused an issues for any reason it can be uninstalled. In the same location a recovery can also take place is the issue with the update can not be fixed by just the installment. 

![image.png](image%2019.png)

This Active hours ensures that the machine does not restart during work hours. While it is automatically set to 8-5 , it should be changed for those who do not work normal hours such as night shift. 

## Windows Logs and Event Viewer

![image.png](image%2020.png)

The event Viewer shows any critical issues or errors that occur on the machine. 

![image.png](image%2021.png)

By looking at the Application logs show all information as it pertains to the apps being used. This can be filtered to better understand a issues that is occurring such as a application that crashes at a certain time to better understand and correct the issues. 

## Windows Device Manager

Is used to change options and update drivers for IoT devices. 

## Task Manager

![image.png](image%2022.png)

This shows what apps and background process are being used and be used to kill or end the task. This is good is a app is no longer responding and needs to be killed. This is also good to see what apps are using a large amount of resources. 

## Windows CMD prompt

```bash
cd #change directory 

cd .. # change dir back 

ipconfig # give us the networking info for the computer 

/? # will bring up the help menu for most commands 

ping # will verify the connection to the ip

```

## Windows Task Scheduler

![image.png](image%2023.png)

This menu allows shows what tasks art scheduled to be executed 

## Create Task

![image.png](image%2024.png)

![image.png](image%2025.png)

![image.png](image%2026.png)

![image.png](image%2027.png)

![image.png](image%2028.png)

Task Scheduler is a amazing tool that allows us to automate task to run in the background to save time. In this case I scheduled a disk cleanup to be run each day.