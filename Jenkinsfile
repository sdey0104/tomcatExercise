pipeline {
    agent any

    tools {
        maven 'Localmaven'
    }

    stages {

        stage('Initialize'){

            steps{
                sh '''
                echo "PATH = ${PATH}"
                echo "M2_HOME = ${M2_HOME}"
                '''
            }

        }

        stage('Build'){
            steps{
                echo 'Hellow World'
            }
        }

        // stage ('Build Servlet Project') {
        //     steps {
        //         /* Maven step */
        //         bat 'mvn clean package'
        //     }
        //     /*Post-build actions*/
        //     post {
        //         success {
        //             echo 'Now Archiving...'

        //             archiveArtifacts artifacts : '**/*.war'
        //         }
        //     }
        // }

        // stage ('Deploy Build in Staging Area') {
        //     steps {
        //         build job : 'Deploy_StagingArea_Pipeline'
        //     }
        // }

        // stage ('Deploy Build in Production Environment') {
        //     steps {
        //         timeout (time: 5, unit: 'DAYS') {
        //             input message : 'Approve PRODUCTION Deployment?'
        //         }

        //         build job : 'Deploy_Production_Pipeline'
        //     }

        //     post {
        //         success {
        //             echo 'Deployment on PRODUCTION is Successful'
        //         }

        //         failure {
        //             echo 'Deployment Failure on PRODUCTION'
        //         }
        //     }
        // }
    }
}
