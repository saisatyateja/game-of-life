
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
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
        stage('junit_reports'){
            steps{
                junit '**/surefire-reports/*.xml'
            }
        }
    }    
}
