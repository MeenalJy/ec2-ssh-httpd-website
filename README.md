#AIM - Setting up and Hosting a Website on an EC2 Instance using SSH.
#Pre-requisites:-
1.	AWS account.
2.	Running EC2 instance which has security roles of HTTP(Edit the inbound rules to allow incoming traffic on port 80 (HTTP) from any IP address (0.0.0.0/0) or specify your desired IP range.)
3.	PuTTY installed on your Windows machine.
#INTRODUCTION 
In this project, I will guide you through the process of connecting to an EC2 instance using SSH and setting up an Apache HTTP server (httpd) to host a small website. 
#STEPS
1.	Connecting to the EC2 Instance via SSH:
i.	Launch PuTTY.
ii.	In the "Category" pane on the left, expand the "Connection" category, then select "SSH".
iii.	In the "Host Name (or IP address)" field, enter the public IP address or DNS name of your EC2 instance.
iv.	In the "Port" field, enter "22" (the default SSH port).
v.	In the "Connection" category, expand the "SSH" category, then select "Auth".
vi.	In the "Private key file for authentication" section, click on the "Browse" button.
vii.	Locate and select the private key file (.pem) you generated earlier.
viii.	Click "Open" to establish the SSH connection.
ix.	PuTTY Security Alert dialog box may appear, indicating that the server's host key is not cached. Click "Yes" to proceed.
x.	If the SSH connection is successful, a terminal window will open, and you will be prompted to log in as the default user "ec2-user". Press "Enter" to continue.
xi.	Use a valid username or group: If "ec2-user" is not a valid username or group on your system, you'll need to use a different username or group that exists. You can substitute it with an appropriate username or group that you want to grant permissions to. For example, if you have a user named "John" on your system and want to grant Full Control permission to that user for the "key-pair-filename.pem" file, you can use the following command:
icacls <file> /grant John:F
xii.	Congratulations! You are now connected to your EC2 instance via SSH using PuTTY.

2.	Install and Configure HTTPD
i.	Once connected to the EC2 instance, run the following command to update the package repository:
sudo yum update -y
ii.	Install the Apache HTTP Server (HTTPD) by running the following command:
sudo yum install httpd -y
iii.	Start the HTTPD service by running the following command:
sudo service httpd start
iv.	Enable the HTTPD service to start automatically on system boot:
sudo chkconfig httpd on
v.	To test if the HTTPD service is running, open a web browser on your local machine and enter the public IP address or DNS name of your EC2 instance. You should see the Apache default test page. 
3.	Host a Small Website
i.	Create a directory to store your website files:
sudo mkdir /var/www/html/mywebsite
ii.	Move into the website directory:
cd /var/www/html/mywebsite
iii.	Create an index.html file or upload your website files to this directory.
4.	Access Your Website
i.	Open a web browser on your local machine and enter the public IP address or DNS name of your EC2 instance.
ii.	You should now be able to access and view your small website.
#Congratulations! You have successfully connected to an EC2 instance using SSH and installed and configured HTTPD to host a small website. You can now continue to develop and enhance your website on the EC2 instance.




