pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository
                git 'https://github.com/la-belle-femme/jenkins-ansible-terraform-dylan.git'
            }
        }

        stage('List Repository Content') {
            steps {
                // Change into the directory and list the content
                sh '''
                    cd jenkins-ansible-terraform-dylan
                    ls -la
                '''
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                // Run the Ansible playbook (assuming Ansible is installed on the Jenkins agent)
                sh '''
                    cd jenkins-ansible-terraform-dylan
                    ansible-playbook -i inventory.yml playbook.yml
                '''
            }
        }

        stage('Clean Workspace') {
            steps {
                // Clean up the workspace
                cleanWs()
            }
        }
    }
}
