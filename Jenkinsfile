pipeline {
    agent any
    options{
        timeout(time: 15, unit: 'MINUTES')
        disableConcurrentBuilds()
    }
    environment {
        project ="expense"
        course ="devops"
        DEPLOY_TO = "production"
        branch="master"
    }
     parameters {
        string(name: 'PERSON', defaultValue: 'Mr aditya', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages{
        stage('build'){
            steps{
                echo "this is build"
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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
            when {
                environment name: 'DEPLOY_TO', value: 'production'
                expression { return env.branch == 'master' }
                }


             // input {
            //     message "Should we continue?"
            //     ok "Yes, we should."
            //     submitter "ARUN"
            //     parameters {
            //         string(name: 'PERSON', defaultValue: 'siri', description: 'Who should I say hello to?')
            //     }
            // }
            steps{
                echo "this is deploy new update"
            }
        }
        stage('parallel'){
            parallel{
                stage('homepage') {
                    
                    steps {
                        echo "open homepage"
                    }
                }
                stage('upload') {
                   
                    steps {
                        echo "upload images"
                    }
                }
                stage('post') {
                    
                    steps {
                        echo "post"
                    }
                }
        
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
