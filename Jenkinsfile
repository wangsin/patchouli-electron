node {
    stage('test'){
     sh 'npm install';
     sh 'npm run unit && npm run e2e';
    }

    stage('unit'){
     sh 'npm install';
     sh 'karma start test/unit/karma.conf.js';
    }

    stage('deploy-using-scm'){
     sh 'node .electron-vue/build.js && electron-builder --dir';
    }
}
