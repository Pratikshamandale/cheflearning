#!/usr/bin/env groovy

// Loads the standardBuild function/step from workflowLibs.git/vars/standardBuild.groovy
// and invokes it.

node('master'){

def job = env.JOB_NAME.split('/')
def job_name= job[0]
def branch_name = job[1]
def build_num=env.BUILD_NUMBER

try
{
stage 'First'
echo "hi"
//build job: 'date', parameters: [[$class: 'StringParameterValue', name: 'var', value: '10.10.6.105']]
echo env.JOB_NAME

println job_name

println branch_name

//git branch: 'new-one' , credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'
//git branch: 'new-branch-1', credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'


String[] git_branch_name= branch_name.replaceAll("%2F","/")

println git_branch_name

//git branch: 'new-one' , credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'
git branch: "${git_branch_name}", credentialsId: '1b4c58ed-4fbc-4be0-97e6-dcf63419b44b', url: 'https://github.com/Pratikshamandale/cheflearning.git'




stage 'Second'
echo "Second"

echo "new branch added"

echo "third branch "
sh "l"
echo "fourth branch"

echo "check check"

echo "check check check"

}

catch(Exception e)
{


stage 'Email Notification'

println "Build failed"


sh "git log --after 1.days.ago | grep Author | cut -d'<' -f2|cut -d'>' -f1 > author"
sh "awk '!seen[\$0]++' author > uniqueAuthor"

def lines = readFile("uniqueAuthor")

String[] linesFile = lines.replaceAll("\n",",")


println "Mails will be send to : ${linesFile}monali.reddy@opexsoftware.com"

def url = "http://52.91.44.91:8080/job/email_test_pipeline/job/${branch_name}/${build_num}/console"

println url

println "---------------------------------------------------------------"
sh "cat /var/lib/jenkins/jobs/jenkinsfile_multibranch/branches/new-one/builds/${build_num}/log"
println "---------------------------------------------------------------------"

//mail bcc: '', body: "ILP code did not succesfully pass the build and unit-test jobs in the Continuous Integration pipeline.\nFor more details go to : ${url} ", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/plain', replyTo: '', subject: "Failed report -${branch_name}", to: "${linesFile}monali.reddy@opexsoftware.com"
//mail bcc: '', body: 'ILP code did not succesfully pass the build and unit-test jobs in the Continuous Integration pipeline. ', cc: '', charset: 'UTF-8', from: '', mimeType: 'text/plain', replyTo: '', subject: "Test Multibranch", to: 'pratiksha.mandale@opexsoftware.com,monali.reddy@opexsoftware.com'

sh "exit 1"
}

}

