pipeline {
    agent any
    options{
        timeout(time: 15, unit: 'SECONDS')
        disableConcurrentBuilds()
    }
    environment {
        project ="expense"
        course ="devops"
    }
    stages{
        stage('build'){
            steps{
                echo "this is build"
                sh """
                  sleep 10
                """
            }

        }
        stage('test'){
            steps{
                echo "this is test"
                echo "project is $project"
                echo "course is $course"
            }
        }
        
         stage('deploy'){
            input {
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'siri', description: 'Who should I say hello to?')
                }
            }
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
