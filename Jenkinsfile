pipeline {
    agent any

    

    stages {
        stage('Clean') {
            steps {
                // Get some code from a GitHub repository
                //git url:'https://github.com/mayureshmudrale/spring-petclinic.git',branch:'main'

                // // Run Maven on a Unix agent.
                // sh "mvn -Dmaven.test.failure.ignore=true clean package"

                // // To run Maven on a Windows agent, use
                 bat "mvnw clean "
            }
            

            // post {
            //     // If Maven was able to run the tests, even if some of the test
            //     // failed, record the test results and archive the jar file.
            //     success {
            //         junit '**/target/surefire-reports/TEST-*.xml'
            //         archiveArtifacts 'target/*.jar'
            //     }
            // }
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

