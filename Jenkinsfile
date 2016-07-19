 node ('linux'){
  stage 'Build and Test'
  checkout scm
  build job: 'date', parameters: [[$class: 'StringParameterValue', name: 'var', value: '10.10.6.105']]
}
