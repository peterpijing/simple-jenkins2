node('master'){
    def mvnHome = '/var/jenkins_home/tools/hudson.tasks.Maven_MavenInstallation/Maven_3.3'
    stage 'checkout'
    echo 'Checking out source code'
    git url: 'https://github.com/predic8/simple-jenkins2'
    
    stage 'compile'
    echo "compile"
    sh "${mvnHome}/bin/mvn compile"
    
    stage 'test'
    echo "Test"
    sh "${mvnHome}/bin/mvn test"
    
    stage 'User Acceptance'
    timeout(time: 10, unit: 'SECONDS') {
        input 'Alles Ok'
    }
    
    stage 'Deploy'
    echo 'Deploy'
}
