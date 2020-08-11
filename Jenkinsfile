pipeline {
    agent any
        
     // using the Timestamper plugin we can add timestamps to the console log
    options {
        timestamps()
    }
     stages{
    //    stage("SCM"){
    //       steps{
    //            echo "git clone"
    //            git branch: 'dev', credentialsId: 'Docker login', url: 'https://github.com/wardviaene/jenkins-course.git'
    //        }
    //     }
        stage("Build"){
            steps{
                echo "Build start"
                nodejs('node') {
                    sh 'npm install'
                }    
                    
            }
            post{
                always{
                    echo "====++++always++++===="
                }
                success{
                    echo "====++++A executed successfully++++===="
                }
                failure{
                    echo "====++++A execution failed++++===="
                }
        
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
