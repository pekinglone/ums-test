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
                    source getversion.sh
                    echo ${version}
                    #for i in ${APP_NAME[@]} 
                    #do
                    #    echo ${i}
                    #done

                    echo "######"
                    #for j in `cat local.config | awk '{print $1}'` 
                    #do
                    #    echo ${j}
                    #done
            }
        }
    }
    post {
        always {
          cleanWs()
        }
    }    
}
