node {
    def container
    stage('buildimage'){
        container=docker.image('node:10.14').inside('-p 4000:3000 --name jenkinstest-${BUILD_NUMBER}'){
            sh 'mkdir -p /usr/src'
            sh 'cd /usr/src'
            echo 'Getting source code...'
            checkout scm
            echo 'Building dependencies...'
        sh 'npm i'
        echo 'Testing...'
        sh 'npm test'
        }
    } 

    // stage('Checkout') {
    //     sh 'mkdir -p /usr/src'
    //     sh 'cd /usr/src'
    //     echo 'Getting source code...'
    //     checkout scm
    // }

    // stage('Build') {
    //     echo 'Building dependencies...'
    //     sh 'npm i'
    // }

    // stage('Test') {
    //     echo 'Testing...'
    //     sh 'npm test'
    // }

    // stage('Publish') {
    //     echo 'Publishing Test Coverage...'
	// 	publishHTML (target: [
	// 		allowMissing: false,
	// 		alwaysLinkToLastBuild: false,
	// 		keepAll: true,
	// 		reportDir: 'coverage/lcov-report',
	// 		reportFiles: 'index.html',
	// 		reportName: "Application Test Coverage"
	// 	])
    // }
}

// node('staging') {
//     stage('Checkout') {
//         echo 'Getting source code...'
//         checkout scm
//     }

//     stage('PM2 Install') {
//         echo 'Installing PM2 to run application as daemon...'
//         sh "npm install pm2 -g"
//     }

//     stage('Build') {
//         echo 'Building dependencies...'
//         sh 'npm i'
//     }

//     stage('Test') {
//         echo 'Testing...'
//         sh 'npm test'
//     }

//     stage('Run Application') {
//         echo 'Stopping old process to run new process...'
//         sh '''
//         npm run pm2-stop
//         npm run pm2-start
//         '''
//     }
// }


