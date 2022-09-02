# codedeploy

# To setup jenkins server in docker

docker build -t jenkins .

docker run -d -p 80:8080 --restart=on-failure --name jenkins -v jenkins_home:/var/jenkins_home jenkins

# code deploy agent installation

yum install -y ruby

cd /tmp

wget https://aws-codedeploy-eu-central-1.s3.amazonaws.com/latest/install;

chmod +x ./install

./install auto

service codedeploy-agent start

ref link: https://aws.amazon.com/blogs/devops/setting-up-a-ci-cd-pipeline-by-integrating-jenkins-with-aws-codebuild-and-aws-codedeploy/

# plugins

aws codedeploy

aws steps

# Create 3 IAM roles
1). create service role for codedeploy service which have codedeploy full access policy is attached to the service role.

2).Iam role with s3 full access and code deploy full access policies, and attach to Jenkins ec2 instance so jenkins will upload zip file to s3 bucket and create codedeploy deployment.

3).Create Iam role wth s3 full access policy and attach it to application ec2 to allow codedeploy agent to download the zip file from s3 bucket as part of deployment.
