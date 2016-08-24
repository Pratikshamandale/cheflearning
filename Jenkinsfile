#!/usr/bin/env groovy

// Loads the standardBuild function/step from workflowLibs.git/vars/standardBuild.groovy
// and invokes it.

node('master'){
stage 'First'
echo "hi"
//build job: 'date', parameters: [[$class: 'StringParameterValue', name: 'var', value: '10.10.6.105']]
echo env.JOB_NAME

def job = env.JOB_NAME.split('/')
def branch_name = job[0]

git branch: '${branch_name}' , credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'



stage 'Second'
echo "Second"

echo "new branch added"

echo "third branch "

echo "fourth branch"
}
