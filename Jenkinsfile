node {
    stage('prepare-npm'){
     env.NODEJS_HOME="${tool 'jenkins-nodejs-16x64'}"
     env.PATH="${env.NODEJS_HOME}/bin:${env.PATH}"
     sh 'echo $PATH';
     sh 'env';
     sh 'npm --version';
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
