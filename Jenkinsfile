pipeline {
  // agent { label "Jenkins-Agent"}
  tools {
    jdk "Java21"
    maven "Maven3"
  }

  stages {
    stage("Cleanup Workspace") {
      steps {
        cleanWs()
      }
    }
    
    stage("Checkout from SCM"){
      steps {
        git branch: 'main', credentilasId: 'github', 'url': 'https://github.com/yansetiaji/register-app'
      }
    }

    stage("Build Application"){
      steps {
        sh "mvn clean package"
      }
    }

    stage("Test Application"){
      steps {
        sh "mvn test"
      }
    }
  }
  
}
