# How-to-Create-Static-Website-AWS-VS-Code
How to Create Static Website  using AWS, html files &amp; VS Code
Here are the steps to create a static website using Terminal/VisualCode, AWS 
Create User
1. The first thing you need to do it create an Amazon AWS Account
2. Create an IAM Account:
   a. search IAM then click Create User 
   b. enter name of user 
   c. Check "Provide user access to AWS Management Console"
   d. Select "I want to create an IAM user"
   e. Create Password and make note of it
   f. Attach policies directly and select/search for AdministerAccess -next
   g. Click Create User

3. Go to the user that you just created
   a.Select security credentials - create access key- other- create access key
   b. Make sure that you download the csv file and store it in a safe place

4. Log out of AWS and log in with the credentials of the new user that was created. You will need the user name, password and account ID.

CREATE EC2 
IN AWS
1. Search "EC2" and select launch instance
2. Enter a Name
3. CLick "Browse More AMIs and search for Centos under "AWS MarketPlace AMI"
4. Select Ubuntu Server 22.04 "FREE TIER"
5. In Instance type select, "t2.micro" "FREE TIER ELIGIBLE"
6. Under key pair, select "create a new key pair"
   Give the key pair a name
    a. Select RSA
    b. Private key: .pem
    c. Select "Create Key Pair
    d. The key pair will be downloaded
7. Click Launch Instance
8.  Go to the Instance you created and wait until the instance state is "running" and status check is in green
9.  Click on The Instance 
    a. Security
    b. Under security groups and select the security group name
    c. Under inbound rules, select "edit inbound rules"
    d. Select "add rule" and add the following rules:
        type: SSH           Source: MyIP
        type: HTTP        Source: MyIP

 10. Go to your Instance
    a. Click Connect
    b. Under SSH Client, copy the ssh -i..... that is under example.

SSH
1. Open Visual Code/Terminal
2. cd into the directory that you downloaded the key pairs for for the EC2. For example, if it is in your download folder: cd/ download. ls to make sure your file is in the right folder.
3. Paste the link that you copied in step 10 above
   a. if you get an error stating that Permissions 0644 for 'nameofkeyparir.pem' are too open: Perform the following
   chmod 400 nameofkeypair.pem, then past the ssh link again
   
Adding HTML Files

Go to www.tooplate.com and download the file in this link:

    https://www.tooplate.com/view/2137-barista-cafe
    Make sure that it is saved in the same folder that you're working in i.e. what ever folder you cd into.
    
Paste the following command to check if httpd is active

a. sudo apt update

b. sudo apt install apache2 wget unzip -y

c. wget https://www.tooplate.com/zip-templates/2137_barista_cafe.zip

d. unzip 2137_barista_cafe
d. ls
e. cp -r 2137_barista_cafe/* /var/www/html
f. systemctl restart apache2

Go to EC2 instance in AWS. 
    Copy the public IPV4 address and paste it in your browser. The website should be up and running.

    Make sure that you terminate your instance.

    
Once done, your website should look like this:

![Screen Shot 2024-06-01 at 12 19 34 PM](https://github.com/Marie623/How-to-Create-Static-Website-AWS-VS-Code/assets/135767885/41863318-6c65-41a5-8002-873fdb755b36)

![Screen Shot 2024-06-01 at 12 21 53 PM](https://github.com/Marie623/How-to-Create-Static-Website-AWS-VS-Code/assets/135767885/8131f9f8-bbde-4f77-94a2-afd137ac633d)

![Screen Shot 2024-06-01 at 12 22 49 PM](https://github.com/Marie623/How-to-Create-Static-Website-AWS-VS-Code/assets/135767885/76fbc3f5-604e-43de-9842-f4efc4622982)



   
