pipeline{
agent any
  tools{
    maven 'Maven'
  }
  stages{
    stage('Checkout'){
      steps{
        git branch:'main',url:'https://github.com/chinmayiii/mavenlistvedio.git'
      }
    }
    stage('Build'){
      steps{
        sh 'mvn clean package'
      }
    }
    stage('Test'){
      steps{
        sh 'mvn test'
      }
    }
    stage('Run Application'){
      steps{
        sh 'mvn exec:java -Dexec.mainClass="com.example.App"'
      }
    }
  }
  post{
    success{
      echo 'Build and deployment succesfull'
    }
    failure{
      echo 'Build failed'
    }
  }
}
