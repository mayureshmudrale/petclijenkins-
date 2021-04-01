pipeline {
    agent any

    

    stages {
        stage('Clean') {
            steps {
              
                 bat "mvn clean "
            }
            

        }
        stage('compile'){
             steps{bat "mvn compile "}
             
            
            
        }
        stage('test'){
            steps{
                bat "mvn test "
            }
                post {
                // If Maven was able to run the tests, even if some of the test
                // failed, record the test results and archive the jar file.
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                   // archiveArtifacts 'target/*.jar'
                }
            }
        }
        
        stage('package'){
           steps{ bat "mvn package"}
        }
    }
}
