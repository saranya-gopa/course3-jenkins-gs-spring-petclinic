echo "Hi world"
node{
    stage("checkout"){
    sh "ls"
    git branch:'main', url: 'https://github.com/saranya-gopa/course3-jenkins-gs-spring-petclinic.git'
    sh "ls"
    }
    stage ("build"){
        sh "./mvnw package"
    }
    stage("capture"){
        archiveArtifacts '**/target/*.jar'
        jacoco()
        junit stdioRetention: '', testResults: '**/target/surefire-reports/TEST*.xml'
    }
}
