def gv

pipeline{

    agent any

    stages{
        stage("init"){
             
            steps{
                script{
                    gv = load 'script.groovy'

                }
            }
        }
        stage("build"){
            steps{
                script{
                    gv.buildApp()
                }
            }
        }
        stage("test"){
            when{
                expression { 
                    params.RUN_TESTS == true 
                 }
            }
            steps{
                script{
                    gv.testApp()
                }
            }
        }
        stage("deploy"){
            steps{
                script{
                    gv.deployApp()
                }
            }
        }
    }
} 
