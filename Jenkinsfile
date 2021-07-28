pipeline {
    agent any

    

    stages {
        stage('checkout') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', url: 'https://github.com/maddurivenkys/jgsu-spring-petclinic.git'
            }
            
        }
        
        stage('build'){
            steps {
            bat 'mvnw.cmd clean package'
            }
        

            post {
            //    // If Maven was able to run the tests, even if some of the test
            //    // failed, record the test results and archive the jar file.
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
              }
            }
        }
    }
}
