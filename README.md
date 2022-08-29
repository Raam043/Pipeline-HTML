# Pipeline
Create IAM Roles - CodeDeploy & EC2CodeDeploy

Create EC2 instance with the following software packages should install

Choose AMI: Amazon Linux 2
alt text

Choose AMI role as EC2CodeDeploy
alt text

Choose User Data: for installing required packages.
#!/bin/bash
sudo yum -y update
sudo yum -y install ruby
sudo yum -y install wget
cd /home/ec2-user
wget https://aws-codedeploy-us-east-2.s3.us-east-2.amazonaws.com/latest/install
sudo chmod +x ./install
sudo ./install auto
sudo yum install -y python-pip
sudo pip install awscli

alt text

Security groups: which enable port SSH port 22 and HTTP 80 for application
alt text

Add tags to your EC2 instance
alt text

Launch instance

Makesure that your bucket should enabled version
alt text

Goto CodeDeploy Create Application

Create a DeploymentGroup

Moving Your Application Into GitHub
for more details Click Here If the application files that you want to deploy are not already in a GitHub repository, you’ll need to set that up. Here’s how you can do it with the getting started sample application. First, download the application files. These examples use Linux / Unix commands.


mkdir codedeploy-sample
cd codedeploy-sample
curl -O http://s3.amazonaws.com/aws-codedeploy-us-east-1/samples/latest/SampleApp_Linux.zip


You can upload SampleApp_Linux.zip file on S3 for further automatic deployment on CodeDeploy Pipeline
