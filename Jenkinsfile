pipeline {
    agent any
    stages {
        stage('git clone source 1') {
            steps {
                dir("jenkins_resouce_for_labs") {
                    checkout([
                            $class: 'GitSCM',
                            branches: [[name: 'main']],
                            extensions: [],
                            submoduleCfg: [],
                            userRemoteConfigs: [[url: 'https://github.com/lenguyenkhoi21/jenkins_resouce_for_labs']]
                    ])
                }
            }
        }

        stage('build source 1') {
            steps {
                dir("jenkins_resouce_for_labs") {
                    sh('yarn install')
                }
            }
        }

        stage('git clone source 2') {
            steps {
                dir("example-aws-front-end") {
                    checkout([
                            $class: 'GitSCM',
                            branches: [[name: 'main']],
                            extensions: [],
                            submoduleCfg: [],
                            userRemoteConfigs: [[url: 'https://github.com/lenguyenkhoi21/example-aws-front-end.git']]
                    ])
                }
            }
        }

        stage('build source 2') {
            steps {
                dir("example-aws-front-end") {
                    sh('yarn install')
                }
            }
        }
    }
}
