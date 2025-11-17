pipeline {
  agent any
  options { timestamps() }

  stages {
    stage('Checkout') {
      steps { checkout scm }
    }

    stage('Install (optional)') {
      steps {
        script {
          sh '''
if [ -f package.json ]; then
  echo "Installing npm dependencies..."
  npm ci --silent || npm install --silent
else
  echo "No package.json — skipping install"
fi
'''
        }
      }
    }

    stage('Archive') {
      steps {
        archiveArtifacts artifacts: '**/*', excludes: 'node_modules/**,.git/**'
      }
    }
  }

  post { always { cleanWs() } }
}
