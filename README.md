# How-to-Create-Static-Website-AWS-VS-Code
How to Create Static Website  using AWS, html files &amp; VS Code
Here are the steps to create a static website using Terminal/VisualCode, AWS 
Create User
1. The first thing you need to do it create an Amazon AWS Account
2. Create an IAM Account:
   search IAM then click Create User 
   enter name of user 
   Check "Provide user access to AWS Management Console"
   Select "I want to create an IAM user"
   Create Password and make note of it
   Attach policies directly and select/search for AdministerAccess -next
   Click Create User

3. Go to the user that you just created
   Select security credentials - create access key- other- create access key
   Make sure that you download the csv file and store it in a safe place

4. Log out of AWS and log in with the credentials of the new user that was created. You will need the user name, password and account ID.

CREATE EC2 
IN AWS
1. Search "EC2" and select launch instance
2. Enter a Name
3. Select "Amazon Linux 2023 AMI"
4. In Instance type select, "t2.micro"
5. Under key pair, select "create a new key pair"
   Give the key pair a name
    Select RSA
    Private key: .pem
    Select "Create Key Pair
    The key pair will be downloaded
6. Under Network settings
   Check "Allow SSH traffic from" select MY IP
7. Click Launch Instance
8. Go to the Instance you created and wait until the instance state is "running" and status check is in green
9. Click on The Instance 
    Security
    Under security groups and select the security group name
    Under inbound rules, select "edit inbound rules"
    Select "add rule" and add the following rules:
        type: SSH           Source: MyIP
        type: Custom TCP          Source: MyIP

 10. Go to your Instance
        Click Connect
        Under SSH Client, copy the ssh -i..... that is under example.

SSH
1. Open Visual Code/Terminal
2. cd into the directory that you downloaded the key pairs for for the EC2. For example, if it is in your download folder: cd/ download. ls to make sure your file is in the right folder.
3. Paste the link that you copied in step 10 above
   if you get an error stating that Permissions 0644 for 'nameofkeyparir.pem' are too open: Perform the following
   chmod 400 nameofkeypair.pem, then past the ssh link again
   
Adding HTML Files
Paste the following command to check if httpd is active
sudo apt update
sudo apt install apahe2 wget unzip -y
wget https://www.tooplate.com/zip-templates/2137_barista_cafe.zip
unzip 2137_barista_cafe






   
