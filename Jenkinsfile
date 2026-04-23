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
        sh 'python -m venv %VENV%'
        sh '%VENV%\\Scripts\\python -m pip install --upgrade pip'
        sh '%VENV%\\Scripts\\pip install -r requirements.txt'
      }
    }
    stage('Run the tests'){
      steps{
        sh '%VENV%\\Scripts\\python manage.py test'
      }
    }
  }
}
