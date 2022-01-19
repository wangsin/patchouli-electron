def GIT_AUTH = "60a550e4-1e6b-49af-a477-943c1279b83a"
def PROJECT_GIT_URL = "http://gitea.inrouter-karmatech.top/wangsin/patchouli-electron.git"
def GIT_BRANCH = "master"


node {
    stage('prepare-npm'){
     env.NODEJS_HOME="${tool 'jenkins-nodejs-16x64'}"
     env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
     sh 'npm --version';
    }
    stage('fetch-code'){
     checkout([$class: 'GitSCM', branches: [[name: "${GIT_BRANCH}"]], extensions: [], userRemoteConfigs: [[credentialsId: "${GIT_AUTH}", url: "${PROJECT_GIT_URL}"]]])
     sh 'pwd && ls';
    }
    stage('test-unit'){
     sh 'npm install';
     sh 'npm run unit && npm run e2e';
    }

    stage('test-karma'){
     sh 'npm install';
     sh 'karma start test/unit/karma.conf.js';
    }

    stage('build-release'){
     sh 'node .electron-vue/build.js && electron-builder --dir';
    }
}
