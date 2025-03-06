pipeline {
 agent none
 stages{
  stage("build and SonarQube Analysis")
  {
   agent any
    steps {
	 withSonarQubeEnv('sonarproject
')
	 {
	  sh "mvn clean package sonar:sonar -Dsonar.projectKey=sonarproject
 -Dsonar.projectName='sonarproject
'"
	 }
	}
  }
 }
}
