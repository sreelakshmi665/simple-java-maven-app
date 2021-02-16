pipeline{
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }
  }
  stages {
    stage('Maven-Clean'){
      steps{
        sh 'mvn clean'
      }
    }
    stage('Maven-Compile'){
      steps{
        sh 'mvn compile'
      }
    }
    stage('Maven_Test'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Maven-Package'){
     try{ 
      steps{
        sh 'mvn package-'  
      }
     }catch(Exception e){
       echo "Build failed"
       echo "building after failure"
       sh 'mvn package'
     }

    }
  }
}
