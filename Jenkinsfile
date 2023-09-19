node  {
    
    stage ('code')
    {
        git credentialsId: 'jenkins', url: 'https://github.com/learnsoftwares/maven_demo.git'
    }
    stage ('build')
    {
        bat 'mvn clean verify'
    }
    stage ('deployment')
    {
        deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://localhost:8080/')], contextPath: 'scripteddemo', war: '**/*.war'
    }
}
