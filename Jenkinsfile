cat <<'EOF' > Jenkinsfile
  pipeline {
      agent any
      stages {
          stage('Checkout') {
              steps {
                  git url:
  'https://github.com/TON-USERNAME/landing-page-example.git', branch: 'main'
              }
          }
          stage('Deploy') {
              steps {
                  withCredentials([usernamePassword(credentialsId:
  'alwaysdata', usernameVariable: 'SSH_USER', passwordVariable:
  'SSH_PASS')]) {
                      sh 'sshpass -p "$SSH_PASS" scp -o
  StrictHostKeyChecking=no index.html
  $SSH_USER@ssh-augustinv-pipeline.alwaysdata.net:www/'
                  }
              }
          }
      }
  }
  EOF