
![Screenshot (183)](https://github.com/user-attachments/assets/4c8aa250-171b-42a8-a8f0-3a2a2803b900)
To begin let me show you my adapter settings on my VirtualBox. I have it set to only the internal network.
Just like our Client computer in the previous lab we will access the internet through our Domain Controller.

-----------------------------------------------------------------------------------------------


I will install the Ubuntu 24.04.1 Server. This operating system is CLI so it does not include a GUI. This will be our new splunk server.

-----------------------------------------------------------------------------------------------


![Screenshot (185)](https://github.com/user-attachments/assets/37ea78ab-d9bf-4c9e-afb4-772478b4179d)

Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (186)](https://github.com/user-attachments/assets/7faa26ce-ecc3-4d96-82d7-b73afdc3be2f)

Continue witout updating and click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (187)](https://github.com/user-attachments/assets/0c91a1f0-6993-47c5-9220-aacae454e0ec)

Hover over Done and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (188)](https://github.com/user-attachments/assets/d7bdeb54-3585-4f09-aeaf-514617b70c34)

Hover over Done and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (184)](https://github.com/user-attachments/assets/0c5bddcd-5f77-4739-96b1-67b20abb9d39)

Thanks to DHCP installed on our Domain Controller you can see our Splunk server is instantly assigned an IP address.
For the sake of the Lab we are going to apply a static IP to the Splunk Server later on when we edit the [ sudo nano /etc/netplan/50-cloud-init.yaml ]. Hover over Done
and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (190)](https://github.com/user-attachments/assets/4566c011-89cd-4364-b57f-8814ae26e994)

Hover over Done and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (191)](https://github.com/user-attachments/assets/144eeb2a-f878-4f56-bb45-6a6f0b7cce8a)

Wait for the mirror location to pass the tests and Hover over done and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (192)](https://github.com/user-attachments/assets/8fa4b916-3596-4fe6-9f8e-e406cc1dd0b4)

Hover over Done and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (193)](https://github.com/user-attachments/assets/a5bd5e7e-d7eb-477c-b4b4-fc7033fc9608)

Hover over Done and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (194)](https://github.com/user-attachments/assets/27a1b094-7169-4337-a3a4-94cbd0847aee)

Hover over Continue and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (195)](https://github.com/user-attachments/assets/f4968135-b7a6-49f8-aa71-96cab7950560)

Now enter the information you will use to log-in to the ubuntu server.

-----------------------------------------------------------------------------------------------

![Screenshot (196)](https://github.com/user-attachments/assets/2d575c56-97c2-4426-ae1d-1bc776e6d5a6)

Hover over Continue and Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (197)](https://github.com/user-attachments/assets/03acc994-1b8b-40be-8978-599974524188)

You can choose to check or not check install OpenSSH Server in my case I installed it for a future lab. Hover over Done and Press Enter.

----------------------------------------------------------------------------------------------

![Screenshot (198)](https://github.com/user-attachments/assets/fad659cd-1e39-4a4e-9d01-b0fa60589638)

Scroll Down, hover over Done and press Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (200)](https://github.com/user-attachments/assets/d4dafe67-e664-4b06-b2bd-f856deb007dc)

Let it install and once it's done you will see the option to Reboot Now. Hover over Reboot Now and press Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (201)](https://github.com/user-attachments/assets/3ee4711e-dff5-4b50-ba3f-59e1c84026cd)

It will run through an Install Process and reboot. Once it is done you will be greeted with a splunk login prompt. Now we enter the login information we entered in for our ubuntu server.

---------------------------------------------------------------------------------------------------------------------


![Screenshot (205)](https://github.com/user-attachments/assets/9740fda3-ac0f-45ba-a47e-3991b2efc544)

Using a web browser we will install Splunk Enterprise using a wget command on our Ubuntu Server. Once on the website we can choose to Log in or Signup. I already have an account so I will Login.

-----------------------------------------------------------------------------------------------------

![Screenshot (207)](https://github.com/user-attachments/assets/7fc69757-ed2d-42b5-9b32-9724bfa7407c)

Hover over products and select Free Trials and Downloads.

-----------------------------------------------------------------------------------------------------------

![Screenshot (209)](https://github.com/user-attachments/assets/90877c15-6ef4-46fc-8018-abdab21de4f9)

Select Splunk Enterprise, Select Linux and Copy the .deb wget link.

--------------------------------------------------------------------------------------------------------

![Screenshot (210)](https://github.com/user-attachments/assets/07a39f4c-b6b1-4ae3-b46d-b3e20578bcde)

Enter that wget command into the ubuntu server to install the splunk enterprise .deb file.

-------------------------------------------------------------------------------------------------------

![Screenshot (212)](https://github.com/user-attachments/assets/3e941154-1477-4ecf-889d-f35ceeb3c7d2)

Use the ls -la command and as you can see Splunk 9.3.1 .deb package has been installed. Now we have to depackage and install Splunk Enterprise.

-------------------------------------------------------------------------------------------------------

![Screenshot (213)](https://github.com/user-attachments/assets/fff26469-d8dc-40b7-a3cd-709e1b262dbc)

To unpackage and install we will use the command [ sudo dpkg -i splunk-9.3.1-###########-linux-2.6-amd64.deb ] (replace #### with your specific install number)
It will prompt you to enter your password. Click Enter.

-----------------------------------------------------------------------------------------------------

![Screenshot (223)](https://github.com/user-attachments/assets/43cfd494-1639-47e0-8e6d-43184ad3fa97)

The license agreement will pop up once the install is finished. Hold the space bar until you recieve the prompt to agree with this license and enter y and click Enter

----------------------------------------------------------------------------------------------------------

![Screenshot (248)](https://github.com/user-attachments/assets/6ce9a66a-f16a-496f-ae34-61ab8c3f6c11)

Now we will set our static IP address for the splunk server using [ sudo nano /etc/netplan/50-cloud-init.yaml ]
Click Enter and enter your Password.

--------------------------------------------------------------------------------------------------------------

![Screenshot (255)](https://github.com/user-attachments/assets/606b29f7-eb1b-4e13-84bd-15a44e3ca61f)

In this file we will switch dhcp4 to no, We will add an addresses field and enter the static IP of our chosing. I am setting mine in the scope we defined in our Domain Controller Lab.
We will add a field named nameservers(DNS server), under name servers we will add a field named addresses and enter our DNS server address in this case 172.168.0.1. 
We will add a field named routes, under it we will enter a field - to: default and a field called via: and again adding our Domain Controller IP. 
Click ctrl + X and enter y to save the modified file.

-----------------------------------------------------------------------------------------------------------------

![Screenshot (256)](https://github.com/user-attachments/assets/9d96c166-c4cf-4f3a-920d-f6b0603cff39)

Click Enter.

------------------------------------------------------------------------------------------------------

![Screenshot (257)](https://github.com/user-attachments/assets/43c230ed-6264-459d-a1e0-aa18ba0e1fd2)

Enter command [ sudo netplan apply ] and click Enter.

-------------------------------------------------------------------------------------------------------

![Screenshot (258)](https://github.com/user-attachments/assets/7c13c6f3-54b5-4177-bab0-ea5ee12c7375)

We will now change directories into the splunk directory using [ cd /opt/splunk ]. Click Enter.

---------------------------------------------------------------------------------------------------------

![Screenshot (259)](https://github.com/user-attachments/assets/ba733d95-792b-4cca-828c-0cfffa4d88ca)

If we use the ls -la command we can see that files access is restricted to a user named splunk. So we must change our user to the splunk user.

----------------------------------------------------------------------------------------------------------

![Screenshot (260)](https://github.com/user-attachments/assets/546d2c68-0daf-432b-af08-3901158d6a33)

We will do this using the command [ sudo - u splunk bash ]. Click Enter.

------------------------------------------------------------------------------------

![Screenshot (262)](https://github.com/user-attachments/assets/c97bd9c2-3e3e-4c65-8642-a142968ebbdf)

If you look at our username it has now changed from a-kkamal@splunk to splunk@splunk meaning we have succesfully 
moved accounts to splunk. Now move Directories to bin using [ cd bin ] so we can start splunk enterprise.

-----------------------------------------------------------------------------------------------------

![Screenshot (263)](https://github.com/user-attachments/assets/a45281c0-0c73-40e1-98b9-2445b3669a33)

To start splunk we will use the command [ ./splunk start ]. Click Enter.

-----------------------------------------------------------------------------------------------------

![Screenshot (264)](https://github.com/user-attachments/assets/dd6331ea-6ee9-4382-8bdf-9b5c3b217afc)

Splunk has now succesfully been deployed. and using the IP adress of the splunk server with the port 8000 we can access the splunk web server our server is hosting.

-------------------------------------------------------------------------------------------------------

![Screenshot (266)](https://github.com/user-attachments/assets/02e236f1-263e-4554-9194-ec4cb79eebed)

If we go back to our domain controller and head to our web browser we can search for this webpage. Click Enter.

-----------------------------------------------------------------------------------------------

![Screenshot (268)](https://github.com/user-attachments/assets/071d3ffb-7039-46f2-8479-a398cb0eef1f)

It has succesfully been deployed and we can access it using our splunk login we defined earlier.
Now we must install our Splunk Universal Forwader to be able to recieve Logs on our server.

-----------------------------------------------------------------------------------------------------

![Screenshot (270)](https://github.com/user-attachments/assets/20136b1c-ec97-4edc-94fa-49c959eaacbf)

Lets log back into the splunk website to install our universal forwarder. 

--------------------------------------------------------------------------------------------------

![Screenshot (270)](https://github.com/user-attachments/assets/8b1c1466-71f1-4f8b-9ecd-e06b6098a14a)

We will click Download Now for the 64bit Windows version. Allow it to install and run it once it finishes.

---------------------------------------------------------------------------------------------------

![Screenshot (274)](https://github.com/user-attachments/assets/55507053-50c0-4d3c-b554-d07d577ff8ae)

Once the install window pops up check the box to accept the License Agreement. Click Next.

------------------------------------------------------------------------------------------------------

![Screenshot (275)](https://github.com/user-attachments/assets/4e0d2e35-7d6b-4121-8257-f5ff42f91bad)

Enter a Username and you can choose to generate a random password but i will enter my own. Click Next

--------------------------------------------------------------------------------------------------------

![Screenshot (276)](https://github.com/user-attachments/assets/a62bbf67-d39d-4d28-8bd2-c0d5b7177828)

Click Next as we don't have a Deployment Server.

-----------------------------------------------------------------------------------

![Screenshot (277)](https://github.com/user-attachments/assets/a8ad2487-7953-45af-8ef9-507359779dc0)

Here we will enter the static IP of our splunk server and the defualt port of 9997. As our Splunk server is our receiving indexer.

---------------------------------------------------------------------------------------------

![Screenshot (278)](https://github.com/user-attachments/assets/d8a02539-4431-44bd-82f2-b13de92d1421)

Click Yes.

-----------------------------------------------------------------------------------------------------

![Screenshot (279)](https://github.com/user-attachments/assets/09756347-5cf7-4bd1-9c33-7a0621bd7d53)

Click Finsh. 

----------------------------------------------------------------------------------------------------

![Screenshot (281)](https://github.com/user-attachments/assets/25486fe6-ca27-43cf-a0e6-7d5fce6a114f)

Now we move one to configuring our inputs.conf file. This file will tell our splunk universal forwarder what events or data we want to send to our splunk server. To do this we are going to begin by opening file explorer and opening our C: drive.

------------------------------------------------------------------------------------------------
![Screenshot (282)](https://github.com/user-attachments/assets/cb6b911f-ee40-4de8-a002-e2030d3f5081)

Click on Prgram Files > SplunkUniversalForwarder > etc > system > local.


---------------------------------------------------------------------------------------------

![Screenshot (287)](https://github.com/user-attachments/assets/4d1e1fc1-3c8d-4820-8b56-b9bd56c73188)

Here is where we are going to add our inputs.conf file.

-------------------------------------------------------------------------------------------

![Screenshot (288)](https://github.com/user-attachments/assets/acecb4ad-9e5a-427e-abb1-9705257521ed)

Head to the start menu and search for Notepad. Right Click and Open as Administrator.

---------------------------------------------------------------------------------------------

![Screenshot (319)](https://github.com/user-attachments/assets/1a8566b4-2f42-48ac-9ec8-37cb49d3fc22)

I will include my inputs.conf file HERE for you to copy and paste. Now save as, and make sure you save it into Prgram Files > SplunkUniversalForwarder > etc > system > local. Also make sure you dont save it as a text file and save it as a .config file.

-----------------------------------------------------------------------------------------------

![Screenshot (298)](https://github.com/user-attachments/assets/b6804ddc-7455-4a34-8660-8ecb13dce6a7)

Whenever you edit the inputs.config file we need to restart the Universal Forwarding service. Click the start menu and search for Services right click and run it as administrator.

-----------------------------------------------------------------------------------------------

![Screenshot (299)](https://github.com/user-attachments/assets/21dff919-5b9f-48ba-8584-396d71ad7622)

Scroll down until you find SplunkForwarder and click restart on the left side of the services window. You may sometimes get an error saying it can't be stopped just click OK and Click Start.

-----------------------------------------------------------------------------------------------

![Screenshot (302)](https://github.com/user-attachments/assets/f3522c1f-c83b-4e17-a26c-bd3774e04d90)

Now we'll head to our splunk webserver and login. We are goong to configure splunk to recieve the log files we defined in the inputs.config file.

-----------------------------------------------------------------------------------------------

![Screenshot (304)](https://github.com/user-attachments/assets/249657de-b70b-45f5-be7b-98351353fb78)

Once we login we will click on settings in the top right corner and click on indexes.

-----------------------------------------------------------------------------------------------


![Screenshot (305)](https://github.com/user-attachments/assets/69ee73e4-c7af-462a-9f57-038f19f9cbbf)

Indexes are essentially labels to be searched for in a splunk query and a way to label our events. If we use WinEventLog://Security for example it an index that is win_security so if we search for it in the future in a query we can define what we're looking for by searching for that index.

-----------------------------------------------------------------------------------------------

![Screenshot (306)](https://github.com/user-attachments/assets/2137021f-0916-4e33-b701-2468420a73d4)


In the top right corner click on New Index and add the name of you index. We will use the Index win_security for this example.

-----------------------------------------------------------------------------------------------

![Screenshot (307)](https://github.com/user-attachments/assets/97868127-1bac-43fa-9810-2a943c7c06f0)

As you can see win_secuirty has been added to our index list. I will now add the remainder of our indexes we have added to our inputs.config file.

----------------------------------------------------------------------------------------------

![Screenshot (308)](https://github.com/user-attachments/assets/e246f408-77e5-4b80-a31c-cefc0902c750)

We have now added all our new indexes.

-----------------------------------------------------------------------------------------------

![Screenshot (313)](https://github.com/user-attachments/assets/272ae59b-a8dd-43a4-a41e-55c8a6d7312d)


Click Settings in the top right corner and select forwarding and receiving.  

-----------------------------------------------------------------------------------------------

![Screenshot (314)](https://github.com/user-attachments/assets/5cee1d0a-a588-4b6e-bf75-d7e096ff1612)

Click on configure recieving. Now we will be able to set the port our splunk server will be listening to recieve data from the Universal Forwarder.

-----------------------------------------------------------------------------------------------

![Screenshot (315)](https://github.com/user-attachments/assets/11db3319-1a1c-498a-9266-cc7b6d2cd9d7)

If you remember we set it to 9997 the defualt port when we were configuring our Universal Fowarder. Click Save. 

-----------------------------------------------------------------------------------------------

![Screenshot (320)](https://github.com/user-attachments/assets/291a53a4-6826-4743-956d-8c962e59078f)


Click on Apps in the top right corner and select Search & Reporting

-----------------------------------------------------------------------------------------------

![Screenshot (321)](https://github.com/user-attachments/assets/72376ece-2817-4bd7-9a59-f00074f504bc)

Now we have everything configured we are able to enter the query index="win_app" and click search.

-----------------------------------------------------------------------------------------------

![Screenshot (322)](https://github.com/user-attachments/assets/18dc9c1f-82c4-42a2-814f-baa864b80956)

Our query brings up Event logs. 

-----------------------------------------------------------------------------------------------

![Screenshot (323)](https://github.com/user-attachments/assets/596752eb-7e66-456b-8636-b0bdbe719192)

If we take a closer look at the event log we can see the 
LogName = Application
The host it came from which is DC.githubdomain.com
As well as a Source and a Source Type. 
Our configuration has been a Success and we now have event logs being sent to our Splunk Server.
