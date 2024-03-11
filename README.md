# MLOPS_ClassTask_2_i200432
MLOPS Class Task 2

![Screenshot 2024-02-19 092436](https://github.com/Lazer430/MLOPS_ClassTask_2_i200432/assets/90345992/33f84556-4543-485e-b146-fdbba6567f47)

This is a test of the jenkins pipeline

Note for Jenkins on WSL:
1) Install the python-is-python3 from apt on Ubuntu
2) Install python3.10-venv from apt
3) Make sure that all python scripts use venv sytax (python -m pytest.py)
4) Enjoy!
done
done
Note: use ${env.GIT_BRANCH} instead of ${env.BRANCH_NAME}

Output:
Started by GitHub push by Lazer430
Obtained Jenkinsfile from git https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/pipeline-as-a-script
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/pipeline-as-a-script/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git # timeout=10
Fetching upstream changes from https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 3feb12a6cb13372e0fb38b54061eaadddd3224a2 (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 3feb12a6cb13372e0fb38b54061eaadddd3224a2 # timeout=10
Commit message: "Update README.md"
 > git rev-list --no-walk 6b2b80056bd8aac8df14af8fcdc1a5af63d075d2 # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Checkout)
[Pipeline] echo
Checking out to main branch
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/pipeline-as-a-script/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git # timeout=10
Fetching upstream changes from https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git
 > git --version # timeout=10
 > git --version # 'git version 2.34.1'
 > git fetch --tags --force --progress -- https://github.com/Lazer430/MLOPS_ClassTask_2_i200432.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
Checking out Revision 3feb12a6cb13372e0fb38b54061eaadddd3224a2 (refs/remotes/origin/main)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f 3feb12a6cb13372e0fb38b54061eaadddd3224a2 # timeout=10
Commit message: "Update README.md"
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Build)
[Pipeline] echo
Building
[Pipeline] withPythonEnv
[Pipeline] {
[Pipeline] sh
+ make install
python -m pip install --upgrade pip
Requirement already satisfied: pip in ./.pyenv-python/lib/python3.10/site-packages (24.0)
python -m pip install -r requirements.txt
Requirement already satisfied: pytest in ./.pyenv-python/lib/python3.10/site-packages (from -r requirements.txt (line 1)) (8.0.2)
Requirement already satisfied: iniconfig in ./.pyenv-python/lib/python3.10/site-packages (from pytest->-r requirements.txt (line 1)) (2.0.0)
Requirement already satisfied: packaging in ./.pyenv-python/lib/python3.10/site-packages (from pytest->-r requirements.txt (line 1)) (23.2)
Requirement already satisfied: pluggy<2.0,>=1.3.0 in ./.pyenv-python/lib/python3.10/site-packages (from pytest->-r requirements.txt (line 1)) (1.4.0)
Requirement already satisfied: exceptiongroup>=1.0.0rc8 in ./.pyenv-python/lib/python3.10/site-packages (from pytest->-r requirements.txt (line 1)) (1.2.0)
Requirement already satisfied: tomli>=1.0.0 in ./.pyenv-python/lib/python3.10/site-packages (from pytest->-r requirements.txt (line 1)) (2.0.1)
[Pipeline] }
[Pipeline] // withPythonEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Test)
[Pipeline] echo
Testing
[Pipeline] withPythonEnv
[Pipeline] {
[Pipeline] sh
+ make test
python -m pytest test.py
============================= test session starts ==============================
platform linux -- Python 3.10.12, pytest-8.0.2, pluggy-1.4.0
rootdir: /var/lib/jenkins/workspace/pipeline-as-a-script
collected 4 items

test.py ....                                                             [100%]

============================== 4 passed in 0.03s ===============================
[Pipeline] }
[Pipeline] // withPythonEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy)
[Pipeline] echo
Deploying
[Pipeline] script
[Pipeline] {
[Pipeline] echo
Current Branch is:origin/main
[Pipeline] echo
Deploying to main
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
