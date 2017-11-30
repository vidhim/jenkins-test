import groovy.json.JsonOutput

def desc = params.description
def source_code

node() {
   echo "test parameters: $params"
   echo "test"
    stage('Get repo'){
        try{
            sh 'mkdir ' + source_code
			dir(source_code){
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: env.TEST_CRED, url: 'http://jazzoss2811-bitbucketelb-408836908.us-east-1.elb.amazonaws.com:7990/projects/SLF/repos/jazz-ui.git' + service_template + '.git']]])
            }
        sh (script:"git ls-files")
        echo "Get repo stage completed"
        } catch(e){
            echo "error: $e"
        }
    }
}