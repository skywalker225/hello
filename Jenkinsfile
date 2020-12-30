pipeline {
  agent any
  stages {
    
    stage "first step on first node"
    node('first-node') {
      sh "mkdir -p output"
      writeFile file: "output/somefile", text: "Hey look, some text."
      stash name: "first-stash", include: "output/*"
    
    }
    
    stage "second step on second node"
    node('second-node') {
      dir("first-stash") {
        unstash "first-stash"
      }
      sh "ls -la ${pwd()}"
      sh "ls -la ${pwd()}/first-stash"
    }
  }
  
//  agent any
//  stages {
//    stage('Stage 1') {
//      steps {
//        echo 'Helloooow world!'
//      }
//    }
//  }
}
