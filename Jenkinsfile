pipeline{
    agent {
        docker {
            image 'ruby'
        }
    }
    
    stages{
        stage('Biuld'){
            steps {
                echo 'Biulding or Resolve Dependencies!'
                sh 'bundle install'
            }
            
        }
        stage('Test'){
            steps {
                echo 'Running Regression Test!'
            }
        }
        stage('Homologation'){
            steps {
                echo 'Wait for User acceptance'
                input(message:'Go to production?', ok: 'Yes')
            }
        }
        stage('Production'){
            steps {
                echo 'Application is Ready!'
            }
        }
    }
}
