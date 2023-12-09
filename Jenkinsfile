pipeline {
  agent any
  stages {
    stage("Init") {
      steps {
        echo "***** Initialize *****"
        echo "params: "
        echo "********************"
      }
    }
    stage("***** Build lab-portal *****") {
      steps {
        sh "ls"
        sh "cd apps/lab-portal"
        sh "docker run build -t lab-portal:0.0.1 ."
        echo "********************"
      }
    }
    stage("***** Push lab-portal *****") {
      steps {
        echo "Push to docker registry..."
        echo "********************"
      }
    }
    // stage("***** Build lab-portal-service *****") {
    //   steps {
    //     echo "********************"
    //   }
    // }
    // stage("***** Push lab-portal-service *****") {
    //   steps {
    //     echo "********************"
    //   }
    // }
  }
}