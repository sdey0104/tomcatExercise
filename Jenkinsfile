pipeline {
    agent any
    stages {

        stage('Build'){
            steps{
               
              //  echo 'Initiaziling the code file'
                bat 'mvn clean package'

                // for macan linux sh mvn clean package''
              
            }

        

        post{
            success{
                echo 'Now archiving'
 
                archiveArtifacts artifacts : '**/*.war'

                }
            }

        }

        stage('Deploy in staging area') { 
                steps{

                    build job : 'Deploy to Staging env'
                }
        }

        stage('Deploy in production area'){
            steps{
                timeout(time: 5, unit: 'DAYS'){
                    input message: 'Approve PRODUCTION Deployment'
                }

                build job :'Deploy To Prod through Pipeline'
            }

            post{
                success{
                    echo 'Deployed to prod successful'
                }

                failure{
                    echo 'unsuccessful'
                }
            }
        }
    }
} 
