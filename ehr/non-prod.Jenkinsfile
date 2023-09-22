pipeline{
    agent any

    environment{
        def git_url = "https://bitbucket.org/hgrailsbackend/codedeployment-demo.git"
    }

    stages{
        stage('build user') {
            steps {
                wrap([$class: 'BuildUser']) {
                    sh 'echo "Triggered By: ${BUILD_USER}"'
                }
            }
        }

        stage("Clean Up"){
            steps{
                deleteDir()
            }
        }

        stage("Clone Repo"){
            steps{
                git url: "${git_url}", branch: 'master'
            }
        }
    }
}
