pipeline{
    agent any{
        stages{
            stage('build image'){
                steps{
                    sh 'docker build -t notes-app .'
                }
            }
            stage('run container'){
                steps{
                    sh 'docker run -d -p 8080:8080 notes-app'
                }
            }
        }
    }
}