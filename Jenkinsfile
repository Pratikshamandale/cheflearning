#!/usr/bin/env groovy

// Loads the standardBuild function/step from workflowLibs.git/vars/standardBuild.groovy
// and invokes it.

node('master'){
stage 'First'
echo "hi"
//build job: 'date', parameters: [[$class: 'StringParameterValue', name: 'var', value: '10.10.6.105']]
echo env.JOB_NAME

def build_number = "${env.BUILD_NUMBER}"
def job = env.JOB_NAME.split('/')
def job_name = job[0]
def branch_name = job[1]
def git_branch_name= branch_name.replaceAll("%2F","/")
def url_branch_name = git_branch_name.replaceAll("/","%252F")
def error_url = "http://localhost:8080/job/${job_name}/job/${url_branch_name}/${build_number}/console"

println git_branch_name

//git branch: 'new-one' , credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'
git branch: "${git_branch_name}", credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'


println error_url

stage 'Second'
echo "Second"

echo "new branch added:bug/ILP-1577_Sync_Progress_issue_in_upcoming_meetings"

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

