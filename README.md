# codedeploy

# To setup jenkins server in docker

docker build -t jenkins .

docker run -d -p 80:8080 --restart=on-failure --name jenkins -v jenkins_home:/var/jenkins_home jenkins
