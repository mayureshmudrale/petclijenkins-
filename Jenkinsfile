pipeline {
    agent any

    

    stages {
        stage('Clean') {
            steps {
              
                 bat "mvnw clean "
            }
            

        }
        stage('compile'){
             steps{bat "mvnw compile "}
             
            
            
        }
        stage('test'){
            steps{
                bat "mvnw test "
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
           steps{ bat "mvnw package"}
        }
    }
}
