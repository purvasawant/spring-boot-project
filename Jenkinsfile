node() {
    mavenPath=tool name: 'maven-latest', type: 'maven'
    env.PATH = env.PATH+":"+mavenPath+"/bin"
    
    stage('Checkout') {
        checkout changelog: false, poll: false, scm: [$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '4e0ab4e8-ae01-4ef3-91ce-f3a36b81a9fd', url: 'https://github.com/purvasawant/spring-boot-project']]]
    }
    
    stage('Maven build and deploy to artifact') {
        sh "mvn deploy -Dusername=admin -Dpassword=password"
    }
}