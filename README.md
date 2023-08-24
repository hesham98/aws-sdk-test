# aws-sdk-test
This repo for practice running Maven app as a job in Jenkins using dsl-script 
the dsl-script in the Jenkins under process job dsl section
the code :
job('DSL-Tutorial-1-Test') {
    scm {
        git {
            remote {
                url('https://github.com/hesham98/aws-sdk-test.git')
                credentials('admin') 
            }
        }
    }
    triggers {
        scm('H/15 * * * *')
    }
    steps {
        maven('-e clean test')
    }
}
