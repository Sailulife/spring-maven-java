pipeline{
    agent{
        kubernetes{
            yamlFile '.jenkins/agent.yaml'
        }
    }
    stages{
        stage('Maven Test'){
            steps{
                container('maven'){
                    sh 'mvn clean test -f pom.xml -s settings.xml'
                }
            }
        }
        stage('Maven Build'){
            steps{
                container('maven'){
                    sh 'mvn install -DskipTests -f pom.xml -s settings.xml'
                }
            }
        }
    }
}