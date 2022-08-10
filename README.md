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
