pipeline {
    agent any

    environment{
        APP_NAME = "ums-management ums-processor ums-receiver ums-wechat-auth"
        APP_DIR = ""
    }

    stages {
        stage('环境变量') {
            steps {
                script {
                    pwd
                    ls -al
                    
                    source getversion.sh
                    echo ${version}
                }
            }
        }
    }
    post {
        always {
          cleanWs()
        }
    }    
}
