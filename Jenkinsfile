pipeline{
    agent none
        stages{
            stage("Checkout"){
                agent{label "nginx_tst1"}
                steps{
                    git 'https://github.com/TadhgBrady/lab-pg.git'
                    sh "git checkout build-2"
                    echo "Stage 1- Checkout"
                    sh "pwd"
                }
            }
            stage("Copy Files to Nginx"){
                agent{label "nginx_tst1"}
                steps{
                    sh "cp -r * /usr/share/nginx/html"
                }
            }
            stage("Copy Files to python"){
                agent{label "python_tst1"}
                steps{
                    sh "cp -r * /usr/share/nginx/html"
                }
            }
            stage("run python"){
                agent{label "python_tst1"}
                steps{
                        sh "cp -r * /usr/share/jenkins/workspace/Python/server"
                    }
                }
            }
        }
}