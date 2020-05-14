pipeline{
    agent {
        docker {
            image 'qaninja/rubywd'
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
                sh 'bundle exec cucumber -p ci'
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
