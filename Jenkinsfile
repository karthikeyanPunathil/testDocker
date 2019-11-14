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
}
