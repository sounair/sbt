pipeline {
    agent { label 'slave1' }

    

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                

                // Run Maven on a Unix agent.
                sh "ls -l"
                sh "sbt compile"
                sh "sbt package"
                sh "chmod +x ./slack.sh"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            
            }
        }
     post {
        success {
           mail bcc: '', body: "<b>build successful</b><br>", subject: "build success", to: "sounair@gmail.com";  
        }
       
    }
    }
