pipeline{

    agent any
    parameters{
        string(name: 'VERSION', defaultValue: '1.0.0', description: 'Version to deploy on prod')
        choice(name: 'Version', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Whether to run')
        booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'Whether to run tests before deploying')
    }

    stages{
        stage("build"){
            steps{
                echo 'building the application...'
            }
        }
        stage("test"){
            when{
                expression { 
                    params.RUN_TESTS == true 
                 }
            }
        
            steps{
                echo 'testing the application...'
            }
        }
        stage("deploy"){
            steps{
                echo 'deploying the application...'
                echo "deploying version ${params.VERSION}"
            }
        }
    }
} 
