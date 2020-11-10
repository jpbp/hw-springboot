pipeline {
    agent any
    options{
        timestamps()
    }
    stages{
        stage('Compilação e teste'){
            steps{
                sh 'mvn clean package'
            }
        }
        stage('Analise de qualidade'){
            steps{
                sh 'mvn sonar:sonar \
                    -Dsonar.projectKey=PipelineSpringBoot \
                    -Dsonar.host.url=http://192.168.88.20:9000 \
                    -Dsonar.login=2a407a1a6c00d587fb55cb367656ae5122b44961'
            }
        }
        stage('Resultado de analise'){
            steps{
                echo 'foi'
            }
        }
        stage('Salvando artefato'){
            steps{
                echo 'foi'
            }
        }
        stage('Deploy para produção'){
            steps{
                echo 'foi'
            }
        }
    }
    post {
        always {
            echo "Sempre executando no post actions"
        }
        success {
            mail to: 'root@localhost', subject:"Build $BUILD_TAG finalizada com Sucesso", body:"Build concluida"
        }
        failure {
            mail to: 'root@localhost', subject:"Build $BUILD_TAG finalizada com Falhas", body:"Build concluida"
        }
    }

}