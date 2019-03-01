pipeline {
  agent any
  tools {
   maven 'maven3.6.0'
   jdk 'java1.8.0'
 }
 stages {
  stage('Build') {
  steps {
    sh "mvn -B -DskipTests clean package"
    }
    }
 

   stage ('Deploy') {
  steps {
    sh 'java -jar target/my-app-1.0-SNAPSHOT.jar'
    }
    }

   
    
     stage('Test') {
            steps {
                sh 'mvn test'
            }
            
                
            
        
 }
}
}

rtUpload (
    serverId: "http://13.71.125.61:8081/artifactory/webapp/#/artifacts/browse/tree/General/example-repo-local",
    specPath: 'target/my-app-1.0-SNAPSHOT.jar'
)

        /*stage('Deliver') {
            steps {
                sh './jenkins/scripts/deliver.sh'
            }
        }
    }
}*/
