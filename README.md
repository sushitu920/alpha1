# alpha1
name: CI

on: 
  push:
    paths-ignore:
      - '**/*.md'
  pull_request:
    paths-ignore:
      - '**/*.md'

jobs:

  build:

    runs-on: ubuntu-latest
    strategy:
      matrix:
        # The MODULE environment variable is evaluated in build-all.sh to run a subset
        # of the builds. This way, multiple modules can be built in parallel.
        module: [ "module1", "module2", "module3", "module4", "module5", "module6", "module7" ]

    steps:

    - name: "Checkout sources"
      uses: actions/checkout@v1

    - name: "Setup Java"
      uses: actions/setup-java@v1
      
