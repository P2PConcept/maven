node('built-in') {
   stage('ContinuousDownload') 
    {
        git 'https://github.com/P2PConcept/maven.git'
    }
    stage('ContinuousBuild') 
    {
        sh 'mvn package'
    }
    stage('ContinuousDeployment') 
    {
        deploy adapters: [tomcat9(credentialsId: 'c6bec4da-c9af-48ff-8254-60b9bc385ae1', path: '', url: 'http://172.31.91.150:8080')], contextPath: 'credomaster', war: '**/*.war'
    }
    stage('ContinuousTesting') 
    {
        git 'https://github.com/P2PConcept/testingcode.git'
        sh 'java -jar /var/lib/jenkins/workspace/multi_master/testing.jar'
    }
    stage('ContinuousDelivery') 
    {
        deploy adapters: [tomcat9(credentialsId: 'c6bec4da-c9af-48ff-8254-60b9bc385ae1', path: '', url: 'http://172.31.90.253:8080')], contextPath: 'credomaster', war: '**/*.war'
    }
}
