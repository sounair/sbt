pipeline {
    agent { label 'slave1' }

    

    stages {
         stage('Setup parameters1') {
            steps {
                script { 
                    properties([
                        parameters([
                            choice(
                                choices: ['UACC', 'PROD'], 
                                name: 'ENVIRONMENT'
                            )
                             ])
                              ])
                }
            }
         }
        
            
         
stage('deploy Production') {
           when {
                expression { 
                   return params.ENVIRONMENT == 'PROD'
                }
            }
            steps {
                    sh "scp -o StrictHostKeyChecking=no root@10.66.24.183:/develop/scala3-example-project_3-0.1.0.jar /tmp"
                    sh "scp -o StrictHostKeyChecking=no /tmp/scala3-example-project_3-0.1.0.jar root@10.66.24.184:/prod"
                    sh """
                    echo "deploy to PROD"
                    """
                                    
                }
            }
   stage('Deploy to UACC') {
            when {
                expression { 
                   return params.ENVIRONMENT == 'UACC'
                }
            }
            steps {
                 sh "scp -o StrictHostKeyChecking=no root@10.66.24.183:/develop/scala3-example-project_3-0.1.0.jar /tmp"
                 sh "scp -o StrictHostKeyChecking=no /tmp/scala3-example-project_3-0.1.0.jar root@10.66.24.186:/uacc"

                    sh """
                    echo "deploy to UACC"
                    """
                }
            }
   
        }
    
    }
