# travis-build-badge
to show project build status(success/fail) by travic badge.

[![Build Status](https://travis-ci.org/saeed3e/tabs.svg?branch=master)](https://travis-ci.org/saeed3e/tabs)

### Step1: login to [travis](https://travis-ci.org/) account with your [github](https://github.com/) credential  and authorize travis to access your github repositories.
### Step2: Go to "accounts" setting by hoveing on your profile pic.
### Step3: Now Enable the repo(by on/off switch button) as shown in images, for which you want to build test cases.
![picture](https://saeed3e.github.io/travis-build-badge/badge_onoff.png) 
### Step4: add travis.yml in your project root directory.

## travis.yml
```
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
```

### Step5: Commit and push your changes on git.

# Note: 
#### Make sure you already tested your test cases on your local machine to prevent any kind of error.
#### Also your repo contain a valid package.json file to tell travis for your npm dependencies.


 For more detail kinldy refer travis [getting started](https://docs.travis-ci.com/user/getting-started) guide
