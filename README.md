Travis-build-badge

to show project build status(success/fail) by Travis badge.

Build Status

Step1: login to Travis account with your GitHub credential and authorize Travis to access your GitHub repositories.

Step2: Go to "accounts" setting by hovering on your profile pic.

Step3: Now Enable the repo(by on/off switch button) as shown in images, for which you want to build test cases.

picture

Step4: add travis.yml in your project root directory.

travis.yml

sudo: required
language: node_js
node_js:
  - "4"
env:
  - CXX=g++-4.8
addons:
  apt:
    sources:
      - ubuntu-toolchain-r-test
    packages:
      - g++-4.8

before_script:
  - npm install -g grunt-cli
  - npm install

script: 
 - grunt 
 - grunt test
Step5: Commit and push your changes on git.

After these steps, Travis automatically gets to know that there are some changes in your git repo and re-run your build suit.

Note:

Make sure you already tested your test cases on your local machine to prevent any kind of error.

Also, your repo contains a valid package.JSON file to tell Travis for your npm dependencies.

For more detail kindly refer Travis getting started guide
