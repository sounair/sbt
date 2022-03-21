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
        stage('Deploy'){
              sh "scp ./target/scala-3.1.1/scala3-example-project_3-0.1.0.jar root@10.66.24.183:/dev
        
        }
        }
    
    }
