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

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            
            }
        }
     post {
        success {
            sh "curl -d "text=build succssful" -d "channel=jenkins" -H "Authorization: Bearer xoxb-3048076520535-3261197624310-rx4nKN4rdoWk2izk86emrFl3"OST https://slack.com/api/chat.postMessage"
        }
       
    }
    }
