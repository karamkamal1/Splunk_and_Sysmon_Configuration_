# Sysmon Step By Step Guide

![Screenshot (324)](https://github.com/user-attachments/assets/448e04b8-0158-4d96-9048-dcda77f0a705)

We will start on our Domain Controller and head to the internet browser.

----------------------------------------------------------------------------------------------------

![Screenshot (325)](https://github.com/user-attachments/assets/3e6cf7cd-3cca-4fa3-8865-a338efdc8fbe)

We will search for Sysmon Download.

---------------------------------------------------------------------------------------------------

![Screenshot (326)](https://github.com/user-attachments/assets/31891cd9-9ccd-417d-8bcb-2ce47f2d31fa)

Click on the first link. Scroll down on the page and click Download Sysmon.

----------------------------------------------------------------------------------------------------

![Screenshot (327)](https://github.com/user-attachments/assets/60740bf0-3ec8-4fc8-ae2e-a6057b523df5)

Once it has finished installing, head to the download folder and right click on the compressed Sysmon folder.
Select Extract All.

-----------------------------------------------------------------------------------------------------

![Screenshot (328)](https://github.com/user-attachments/assets/894abbb9-db25-47b8-bea4-3955c09e7320)

Click Extract.

----------------------------------------------------------------------------------------------------

![Screenshot (329)](https://github.com/user-attachments/assets/43a5789b-9a3c-4681-972f-6e0b77b69cf1)

Once we open the extracted folder we can see the installation executables for Sysmon. Close the folder for now and open your Web Browser.

-----------------------------------------------------------------------------------------------------

![Screenshot (330)](https://github.com/user-attachments/assets/abae1b45-ac63-42b3-96ef-b32744c5ef7d)

We will search for sysmon olaf configuration. Olaf configuration is a prebuilt configuration file that really assists in logging on Sysmon.

-------------------------------------------------------------------------------------------------------

![Screenshot (331)](https://github.com/user-attachments/assets/a324884b-7b1f-44cb-a033-17ed00f620e7)

We will click on the github link.

-----------------------------------------------------------------------------------------------------

![Screenshot (332)](https://github.com/user-attachments/assets/b812bff6-7aec-4219-8fbe-aff83c0ade2e)

We will scroll down the repository and click on systemconfig.xml

-----------------------------------------------------------------------------------------------------

![Screenshot (333)](https://github.com/user-attachments/assets/f896257b-82b2-4ed9-9f91-748d83f75e21)

Click raw.

------------------------------------------------------------------------------------------------------------

![Screenshot (334)](https://github.com/user-attachments/assets/51f1d959-45a1-4f50-810b-3d47432c6387)

Right Click and select Save As, make sure it saves as a xml file.

----------------------------------------------------------------------------------------------------

![Screenshot (335)](https://github.com/user-attachments/assets/9246a2b3-e1d3-4c45-aa91-2811bef6e76d)

Click Save. Close the web browser.

------------------------------------------------------------------------------------------------
![Screenshot (336)](https://github.com/user-attachments/assets/9ff9bd99-f792-42eb-a498-0a73318b547c)

Head to the Start Menu and and search for Powershell. Right click it and start it as an Administrator.

---------------------------------------------------------------------------------------------------------

![Screenshot (339)](https://github.com/user-attachments/assets/25a06d65-ad43-4c2b-8f51-12c209ea9de4)

We will navigate powershell to where we have downloaded our Sysmon installer.

---------------------------------------------------------------------------------------------------

![Screenshot (338)](https://github.com/user-attachments/assets/0fcf1b82-c269-4b05-9a7a-06b5f7ba15d9)

We can find that path by navigating to our sysmon folder and copy the path.

-------------------------------------------------------------------------------------------------

![Screenshot (341)](https://github.com/user-attachments/assets/6964cf18-29d6-479c-80c2-d1510dc82911)

After entering our command into Powershell Click Enter. Now we will install Sysmon as well as our configuration file.
We will use the command [ .\Sysmon64.exe -i ..\sysmonconfig.xml ] this will install sysmon64.exe as well as install our config.xml file.

-----------------------------------------------------------------------------------------------------

![Screenshot (342)](https://github.com/user-attachments/assets/cc205ca4-da30-456a-af73-d260ec467179)

Click Agree.

-----------------------------------------------------------------------------------------------------

![Screenshot (343)](https://github.com/user-attachments/assets/81295b07-431d-4df9-a52e-1613ed01b5bc)

Sysmon has now been installed and configured (:
