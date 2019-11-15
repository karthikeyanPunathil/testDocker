node{
  stage('SCM Checkout'){
  git 'https://github.com/BYTA-TECH/testDocker'
  }
  stage('Compile-Package'){
  sh 'mvn install -Dmaven.test.skip=true'
  }
  stage('Build Docker Image'){
  sh 'sudo mvn package -Pprod verify jib:dockerBuild -Dmaven.test.skip=true'
  }
  stage('Push Docker Image'){
      withCredentials([string(credentialsId: 'dockerHub', variable: 'dockerHubPwd')]) {
          sh "docker login -u byta3262 -p ${dockerHubPwd}"
}
    sh 'sudo docker push byta3262/doctor:latest'
  }
}
