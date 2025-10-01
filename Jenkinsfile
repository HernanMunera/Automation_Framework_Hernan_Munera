pipeline { 
    agent any

    tools {nodejs "nodejs"}

    stages {
        stage('Cypress Parallel Test Suit') {
            parallel {
                stage('Slave Node1') {
                    agent {
                        label 'remote_node1'
                    }
                    steps {
                        git url: 'https://github.com/HernanMunera/Automation_Framework_Hernan_Munera.git'
                        sh 'npm install'
                        sh 'npm update'
                        sh 'npm run triggerAllTests-dashboard'
                    }
                }
                stage('Slave Node2') {
                    agent {
                        label 'remote_node2'
                    }
                    steps {
                        git url: 'https://github.com/HernanMunera/Automation_Framework_Hernan_Munera.git'
                        sh 'npm install'
                        sh 'npm update'
                        sh 'npm run triggerAllTests-dashboard'
                    }
                }
            }
        }
    }
}

