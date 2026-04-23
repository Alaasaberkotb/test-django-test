pipeline{
  agent any
  environment{
    VENV = 'venv'
  }
  stages{
    stage('Checkout Out'){
      steps{
        git branch: 'main', url: 'https://github.com/Parth2k3/test-django'
      }
    }
    stage('Set up VENV'){
      steps{
        sh 'python3 -m venv venv'
        sh 'venv/Scripts/pip -m pip install --upgrade pip'
        sh 'venv/Scripts/pip install -r requirements.txt'
      }
    }
    stage('Run the tests'){
      steps{
        sh '%VENV%\\Scripts\\python manage.py test'
      }
    }
  }
}
