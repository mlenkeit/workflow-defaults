on:
  workflow_dispatch: # manual trigger

jobs:
  job1:
    runs-on: ubuntu-latest
    steps:
      - run: exit 0
  job2:
    runs-on: ubuntu-latest
    steps:
      - run: exit 1
  job3:
    runs-on: ubuntu-latest
    needs:
      - job1
      - job2
    steps:
      - run: echo 'Hello'
    
