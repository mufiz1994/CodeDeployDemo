
# Installing the CodeDeploy agent on EC2
```
sudo yum update -y
sudo yum install -y ruby wget
wget https://aws-codedeploy-eu-west-1.s3.eu-west-1.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
sudo service codedeploy-agent status
```


# create a bucket and enable versioning
```
aws s3 mb s3://aws-devops-course-stephane --region eu-west-1 --profile aws-devops
aws s3api put-bucket-versioning --bucket aws-devops-course-stephane --versioning-configuration Status=Enabled --region eu-west-1 --profile aws-devops
```

# deploy the files into S3
```
aws deploy push --application-name CodeDeployDemo --s3-location s3://aws-devops-course-stephane/codedeploy-demo/app.zip --ignore-hidden-files --region eu-west-1 --profile aws-devops
```


# Installing the CodeDeploy agent on EC2(Ubuntu)
```

sudo apt-get update
sudo apt-get install ruby
sudo apt-get install wget
cd /home/ubuntu
wget https://aws-codedeploy-ap-south-1.s3.ap-south-1.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
sudo service codedeploy-agent status
sudo service codedeploy-agent start
sudo service codedeploy-agent status
```
