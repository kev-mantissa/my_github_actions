name: Multiple shells commands
on:
  push:
    branches:
      - "main"
  pull_request:
    types: [closed, assigned, opened, reopened]
jobs:
  run-shell-command:
    runs-on: ubuntu-latest
    steps:
      - name: python commands
        run: |
          import platform
          print(platform.processor())
        shell: python
  run-windows-command:
    runs-on: windows-latest
    needs: ["run-shell-command"]
    steps:
      - name: current directory with powershell
        run: Get-Location
      - name: current directory with bash
        run: pwd
        shell: bash
      - name: print some default env variables
        run: |
          echo "HOME: ${HOME}"
          echo "GITHUB_WORKFLOW: ${GITHUB_WORKFLOW}"
          echo "GITHUB_ACTION: ${GITHUB_ACTION}"
          echo "GITHUB_ACTIONS: ${GITHUB_ACTIONS}"
          echo "GITHUB_ACTOR: ${GITHUB_ACTOR}"
          echo "GITHUB_REPOSITORY: ${GITHUB_REPOSITORY}"
          echo "GITHUB_EVENT_NAME: ${GITHUB_EVENT_NAME}"
          echo "GITHUB_WORKSPACE: ${GITHUB_WORKSPACE}"
        shell: bash
