node('built-in') {
   stage('ContinuousDownload') 
    {
        git 'https://github.com/P2PConcept/maven.git'
    }
    stage('ContinuousBuild') 
    {
        sh 'mvn package'
    }
}
