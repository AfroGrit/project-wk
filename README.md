## Project of the week work: Github Actions 
___
1. github actions?

CI/CD within github, tighter integration

2. workflow
automated process with the following components

  - Listen for particular events 
  ```
  on:  [ push ]

  on:
  pull_request:
    # Sequence of patterns matched against refs/heads
    branches:    
      - main
      - 'mona/octocat'
      - 'releases/**'
      
  ```
  - then run actions
  ```
    steps:
    - name: 'Checkout GitHub Action'
      uses: actions/checkout@v3

    - name: Setup Python ${{ env.PYTHON_VERSION }} Environment
      uses: actions/setup-python@v4
      with:
        python-version: ${{ env.PYTHON_VERSION }}

  ```

  - then run scripts
  ```
      - name: 'Resolve Project Dependencies Using Pip'
      shell: bash
      run: |
        pushd './${{ env.AZURE_FUNCTIONAPP_PACKAGE_PATH }}'
        python -m pip install --upgrade pip
        pip install -r requirements.txt --target=".python_packages/lib/site-packages"
        popd
  ```


  ### credit: [Project of the Week at DataTalks.Club](https://github.com/DataTalksClub/project-of-the-week/blob/main/2023-01-11-github_actions-1.md)


