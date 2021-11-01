pipeline {
    agent any

    environment{
        APP_NAME = "ums-management ums-processor ums-receiver ums-wechat-auth"
        PROJECT_NAME = "ums"
        IMAGE_REGISTRY = "10.29.40.153:1043"
    }

    stages {
        stage('编译代码') {
            steps {
                sh 'echo complie'
                sh '# mvn clean install'
            }
        }
        stage('制作镜像') {
            steps {
         
                    sh '''
                        VERSION=`sh getversion.sh`
                        for i in ${APP_NAME}
                        do 
                            echo "开始制作镜像：" $i " ……"
                            echo "docker build -t ${IMAGE_REGISTRY}/${PROJECT_NAME}/${i}:${VERSION} -f ${i}/Dockerfile"
                            #docker build -t ${IMAGE_REGISTRY}/${PROJECT_NAME}/${i}:${VERSION} -f ${i}/Dockerfile .
                            #docker push ${IMAGE_REGISTRY}/${PROJECT_NAME}/${i}:${VERSION}
                        done
                    '''

            }
        }
    }
    post {
        always {
          cleanWs()
        }
    }    
}
