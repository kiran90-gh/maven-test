
pipeline{
 tools{
        jdk 'JAVA_HOME'
        maven 'M2_HOME'
    }
     agent any
	  
	  stages{
	  
	  stage("checkout"){
	   steps{
	   git 'https://github.com/ashisnishanka/maven-test.git'
	   }
	                  }
	
	   stage("compile"){
	    steps{
		 sh 'mvn compile'
		}
		}
       stage("test"){
	    steps{
		 sh 'mvn test'
		}
		}
	
       stage("package"){
	    steps{
		 sh 'mvn clean package'
                 sh "mv target/*.jar target/myweb.jar"

		}
		}
stage(backup)
		  {
  steps{

nexusArtifactUploader artifacts: [[artifactId: 'app', classifier: '', file: 'target/myweb.jar', type: 'jar']], credentialsId: '8bff6da7-95cc-4f00-b643-2351a20c7356', groupId: 'com.idream', nexusUrl: '13.201.74.18:8081/repository/maven-releases/', nexusVersion: 'nexus2', protocol: 'http', repository: 'maven-releases', version: '1.5'	  
  }
	
}
	}
	}
