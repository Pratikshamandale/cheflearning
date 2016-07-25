#!/usr/bin/env groovy

// Loads the standardBuild function/step from workflowLibs.git/vars/standardBuild.groovy
// and invokes it.
stage 'First'
echo "hi"
build job: 'date', parameters: [[$class: 'StringParameterValue', name: 'var', value: '10.10.6.105']]
echo env.JOB_NAME

stage 'Second'
echo "Second"

echo "new branch added"

echo "third branch "

echo "fourth branch"
