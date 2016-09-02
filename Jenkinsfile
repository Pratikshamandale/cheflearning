#!/usr/bin/env groovy

// Loads the standardBuild function/step from workflowLibs.git/vars/standardBuild.groovy
// and invokes it.

node('master'){
stage 'First'
echo "hi"
//build job: 'date', parameters: [[$class: 'StringParameterValue', name: 'var', value: '10.10.6.105']]
echo env.JOB_NAME

def job = env.JOB_NAME.split('/')
def branch_name = job[1]

println branch_name

//git branch: 'new-one' , credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'
git branch: '{branch_name}', credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'


stage 'Second'
echo "Second"

echo "new branch added"

echo "third branch "

echo "fourth branch"

echo "check check"

echo "check check check"

sh "git log --after 1.days.ago | grep Author | cut -d'<' -f2|cut -d'>' -f1 > author"

sh "awk '!seen[\$0]++' author > uniqueAuthor"

def lines = readFile("uniqueAuthor")

String[] linesFile = lines.replaceAll("\n",",")


println "Mails will be send to : ${linesFile}monali.reddy@opexsoftware.com"

//mail bcc: '', body: 'Testing the multibranch..', cc: '', charset: 'UTF-8', from: '', mimeType: 'text/plain', replyTo: '', subject: 'Test Multibranch', to: "${linesFile}monali.reddy@opexsoftware.com"
//mail bcc: '', body: 'Testing the multibranch', cc: '', charset: 'UTF-8', from: '', mimeType: 'text/plain', replyTo: '', subject: 'Test Multibranch', to: 'pratiksha.mandale@opexsoftware.com,monali.reddy@opexsoftware.com'


}

