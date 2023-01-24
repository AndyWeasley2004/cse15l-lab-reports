# CSE15L Account and Installation Setup Instruction

>In CSE 15L, you will need a a course-specific account to connect with the server. So let's begin!

## Step 1 - Look up your account
* First go to this [link](https://sdacs.ucsd.edu/~icc/index.php) to look up your 15L specific account, and the page should look like this
![image](https://user-images.githubusercontent.com/110661816/212160351-92f478c2-c084-48a8-b9e3-2842f211301c.png)
* Then type your UCSD username (Without @ucsd.edu) and your PID (starts with A). Then, click on submit, and you should see this page
![image](https://user-images.githubusercontent.com/110661816/212160988-d09f7419-c689-41a7-b3e1-d9c03b6c13f4.png)
* Next, you probably need to reset your password, and in this step, **Do NOT press SUBMIT button after you type your new password**, because 
it will always say your password is invalid or used. Instead, you need to press **Enter** directly after you finish typing the confirming password field.
Your mouse should be on the last password field, too.
* If it says change password successfully (or something similiar), you have make the first step!

## Step 2 - Installing VS Code
* Google VS Code and enter the official website
![image](https://user-images.githubusercontent.com/110661816/212161904-d0cec69e-23cd-4cea-9f7f-08a0612cfbf1.png)
* Click on Download
* Then, finish the Installation with the instruction from the installing guide in the software
* After installing, launch your VS Code, if it looks like the page below (or similiar welcome page). Congratualtions!
![image](https://user-images.githubusercontent.com/110661816/212162549-b7a7d750-84bb-4922-9ed1-bf69e1dc127a.png)

## Step 3 - Remotely Connecting
* Open the terminal in your VS Code
* Press the "+" button on the right side, and select bash. It should look like below.

![image](https://user-images.githubusercontent.com/110661816/212162986-8234a978-ee99-4363-9f64-4723a28d9393.png)
* Then, type the command `ssh cs15lwi23zz@ieng6.ucsd.edu`. **Attention: you need to replace cs15lwi23zz with your own account**, which can be found when you finish the first step.

![image](https://user-images.githubusercontent.com/110661816/212163458-ef1292b7-58c5-4d9c-ba3b-29830f2d0e24.png)
* You probably will see this message after pressing enter in the last step:

```
The authenticity of host 'ieng6.ucsd.edu (128.54.70.238)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.     
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

It is very common when you try to login a new server. You can simply type yes and press enter. If you see the following messages, you successfully connect to the CSE basement server.

```
Last login: Thu Jun  2 13:55:30 2022 from 128.54.207.113
Attempting to create directory /home/linux/ieng6/cs15lwi23/cs15lwi23agg/perl5
                             NOTICE 
Authorized use of this system is limited to password-authenticated
usernames which are issued to individuals and are for the sole use of
the person to whom they are issued.

Privacy notice: be aware that computer files, electronic mail and
accounts are not private in an absolute sense.  You are responsible
for adhering to the ETS Acceptable Use Policies, which you can review at:
https://blink.ucsd.edu/faculty/instruction/tech-guide/policies/ets-acceptable-use-policies.html

 Problems, Suggestions, or Feedback

    For help requests, please create a ticket at:
    https://support.ucsd.edu/its

    You may also report issues, suggestions, or feedback by e-mailing root on any system:
    mail -s "Your subject here" root
    Type your message - Ctrl+D to send

 Access our Linux ssh terminals or remote desktops via a web browser at:
    https://linuxcloud.ucsd.edu

    All accounts must be enrolled in Duo for access. No VPN required.


-------------------------------------------------------

Hello cs15lwi23agg, you are currently logged into ieng6-201.ucsd.edu

You are using 0% CPU on this system

Cluster Status
Hostname     Time    #Users  Load  Averages
ieng6-201   10:25:01   8  0.00,  0.06,  0.10
ieng6-202   10:25:01   7  0.00,  0.03,  0.05
ieng6-203   10:25:01   4  0.05,  0.08,  0.08


Thu Jan 12, 2023 10:29am - Prepping cs15lwi23
```

## Step 4 - Try some command!
You can try the following starter command and watch the output
* cd ~
* pwd
* cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/
* cat /home/linux/ieng6/cs15lwi23/public/README.instructor

These are basic commands you need to know. Among them, cd can help you change the directory you are working on. pwd command can show the current working directory on your commputer. cp can copy the file or directory you typed. And cat can concat the file content and print them in the command line. If you type one file directory, it will print it directly as you can see in the result of the last command.

If you want, you can try some your own commands to practice!

>Thre are also commands that cause an error. For example, when you try to change the working directory to a non-exist location. Say cd /home/linux/ieng6/cse100 (assume you don't have this folder), you will see the error message. 
You can also try more to see when other commands will show an error, too.

When you finish your exploration, you can log out from the server by
* press Ctrl-D
* type "exit" in the terminal and run it

Now, you complete your first journey in connecting to a remote server!
