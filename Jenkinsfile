pipeline{
    agent any
    stages{
        stage('1-clonecode'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'git-user', url: 'https://github.com/Etech-Team4/parallel-job.git']]])
            }
        }
        stage('2-parallel-tasks'){
            parallel{
                stage('1-codebuild'){
                    steps{
                        sh 'du -h'
                    }
                }
                stage('2-unittest'){
                    steps{
                        sh 'free -g'
                    }
                }
            }
        }
        stage('3-codequality'){
            steps{
                sh 'lsblk'
            }
        }
        stage('4-backup'){
            steps{
                sh 'cat /etc/passwd'
            }
        }
    }
}
