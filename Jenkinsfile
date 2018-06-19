node('master') {
    stage("Fetch Source Code") {
        git 'https://github.com/TrainingByPackt/Beginning-Continuous-Delivery-With-Jenkins.git'
    }
    
    dir('Lesson5') {
        printMessage('Running Pipeline')
        
        stage("Testing") {
            sh 'apk add python'
            sh 'python test_functions.py'
        }
        
        stage("Deployment") {
          if(env.BRANCH_NAME == 'master') {
            printMessage('Deploying to the master branch')
          }
          else {
            printMessage('No deployment, only build')
          }
        }
        
        printMessage('Pipeline Complete')
    }
}

def printMessage(message) {
    echo "${message}"
}
