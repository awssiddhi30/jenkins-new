pipeline {
    agent any
    stages{
        stage('build'){
            steps{
                echo "this is build"
            }

        }
        stage('test'){
            steps{
                echo "this is test"
            }
        }
         stage('deploy'){
            steps{
                echo "this is deploy new update"
            }
         }
    }
    post {
        always{
            echo "run always"
        }
        success{
            echo "build successsfully"
        }
        failure{
            echo "build failed"
        }
        aborted{
            echo "build aborted"
        }
    } 

}
