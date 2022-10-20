
pipeline{
    agent {
        label 'shopizer'
    }
    stages{
        stage('clone'){
            steps{
                git url: 'https://github.com/saisatyateja/game-of-life.git',
                    branch: 'main'
            }
        }
        stage ('build') {
            steps {
               sh 'mvn package'
           }
        }
       
        stage('archiving-artifacts'){
            steps{
                archiveArtifacts artifacts: '**/game-of-life/target/*.jar', followSymlinks: false
            }
        }
        stage('junit_reports'){
            steps{
                junit '**/game-of-life/surefire-reports/*.xml'
            }
        }
    }    
}
