node {
    stage('test'){
     npm install;
     npm run unit && npm run e2e;
    }

    stage('unit'){
     npm install;
     karma start test/unit/karma.conf.js;
    }

    stage('deploy-using-scm'){
     node .electron-vue/build.js && electron-builder --dir;
    }
}
