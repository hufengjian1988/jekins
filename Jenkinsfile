pipeline {
  agent any
  stages {
    stage('code') {
      parallel {
        stage('code') {
          steps {
            echo 'start code'
          }
        }

        stage('matrix_merge') {
          steps {
            git(url: 'https://codeup.aliyun.com/61bc0540b06145a70d0de4f6/erp_factory/erp_factory_matrix/erp_matrix.git', branch: 'mater', credentialsId: 'fengjian_git', changelog: true)
          }
        }

        stage('server_merge') {
          steps {
            git(url: 'git@codeup.aliyun.com:61bc0540b06145a70d0de4f6/erp_factory/erp_factory_matrix/erp_matrix.git', branch: 'master', changelog: true, credentialsId: 'xx')
          }
        }

        stage('pc_merge') {
          steps {
            git(url: 'git@codeup.aliyun.com:61bc0540b06145a70d0de4f6/erp_factory/erp_factory_matrix/erp_matrix.git', branch: 'master', changelog: true, credentialsId: 'xx')
          }
        }

        stage('server_manual') {
          steps {
            git(url: 'git@codeup.aliyun.com:61bc0540b06145a70d0de4f6/erp_factory/erp_factory_matrix/erp_matrix.git', branch: 'master', credentialsId: 'xx')
          }
        }

        stage('pc_manual') {
          steps {
            git(url: 'git@codeup.aliyun.com:61bc0540b06145a70d0de4f6/erp_factory/erp_factory_matrix/erp_matrix.git', branch: 'master', credentialsId: 'xx')
          }
        }

      }
    }

    stage('build') {
      steps {
        echo 'start build'
      }
    }

  }
}