pipeline{
    agent{
        label 'ANSIBLE'
    }
    triggers{
        upstream(upstreamProjects: 'GOL-Practice-Pipeline' )
        threshold: hudson.model.Result.SUCCESS
    }
    stages{
        stage ('SCM'){
            steps{
                branch 'master'
                git 'https://github.com/rvkrthk/jenkins-tomcat-pipeline.git'
            }
        }
        stage ('ANSIBLE'){
            steps{
                sh 'ansible -i inventory -m ping all'
                sh 'ansible-playbook -i inventory gameoflifedeploy.yaml'
            }
        }

    }
}