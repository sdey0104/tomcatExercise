pipeline {
    agent any
    stages {

        stage('Build'){
            steps{
               
              //  echo 'Initiaziling the code file'
                bat 'mvn clean package'

                // for macan linux sh mvn clean package''
              
            }

        }

        post{
            success{
                echo 'Now archiving'

                archiveArtifacts artifacts : '**/*.war'

            }
        }

    }
}
