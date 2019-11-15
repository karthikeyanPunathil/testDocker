node{
  stage('SCM Checkout'){
  git 'https://github.com/BYTA-TECH/testDocker'
  }
  stage('Compile-Package'){
  sh 'mvn install -Dmaven.test.skip=true'
  }
  
  stage('Push Docker Image'){
      withCredentials([string(credentialsId: 'dockerHub', variable: 'dockerHubPwd')]) {
          sh "docker login -u byta3262 -p ${dockerHubPwd}"
}
    sh 'sudo docker tag doctor byta3262/doctor:v1.0.1'
    sh 'sudo docker push byta3262/doctor'
  }
}
