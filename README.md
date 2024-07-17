# RepoInsight
This is a command line tool that provides statistical insight into one or more GitHub repositories. The tool gathers data on commits, contributors, branches, and tags. It also provides detailed contributor statistics, including the number of commits, lines added, and lines deleted. The tool analyzes both overall and recent contributions and checks for empty commits.

## Setup
The tool requires Python to be installed on your machine. It uses the GitPython and requests libraries. If these are not installed, you can install them using pip:

```
pip install gitpython requests
```

This script also assumes that you have a GitHub PAT (personal access token) set as a path variable.
First, get your PAT from the GitHub website.
Then set that value into a variable "GITHUB_PAT":
* Windows Command Prompt: ```set GITHUB_PAT=YOUR_PERSONAL_ACCESS_TOKEN```
* Windows PowerShell: ```$env:GITHUB_PAT="YOUR_PERSONAL_ACCESS_TOKEN"```
* Linux/Mac: ```export GITHUB_PAT=YOUR_PERSONAL_ACCESS_TOKEN```

## Usage
You can run the tool from the command line as follows:

```
python repoInsight.py --group_url <group_url> --repos_to_clone <repo_1> <repo_2> ...
```

Here, <group_url> is the URL of the GitHub group (e.g., 'https://github.com/SolveCare/') and <repo_1> <repo_2> ... is a space-separated list of repositories that you want to clone and analyze.

If you don't provide the --group_url and --repos_to_clone arguments, the script will prompt you to enter them manually.

## Output
The tool outputs the gathered statistics to the console. It provides an overview of the total number of commits, contributors, branches, and tags across all analyzed repositories. It also lists the top contributors (by number of commits) both overall and recently (within the last three months). Additionally, it presents the top three most active repositories based on the number of commits. If there are any empty commits (commits that added or removed nothing), the tool will alert you.

Sample output (Note: if the repository has not been cloned yet it would do so, in this example they have already been cloned):
``` shell
$ python3 repoInsight.py
Enter GitHub group URL (e.g. 'https://github.com/SolveCare/'): https://github.com/blocksecteam/
Enter repositories to clone separated by space: metasuites audit-reports solana_simplified phalcon_fork_examples Ethernaut_2024_phalcon eth-phishing-detect hookscan Phalcon rustle damn-vulnerable-defi-phalcon-fork metasleuth_resources blocksec_academy defi_poc solana_demo near_demo bitcoinmixing
> Starting repository metasuites
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 114 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository audit-reports
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 76 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository solana_simplified
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 4 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository phalcon_fork_examples
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 15 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository Ethernaut_2024_phalcon
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 14 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository eth-phishing-detect
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 23926 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository hookscan
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 50 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository Phalcon
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 13 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository rustle
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 310 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository damn-vulnerable-defi-phalcon-fork
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 80 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository metasleuth_resources
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 3 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository blocksec_academy
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 20 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository defi_poc
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 20 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository solana_demo
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 240 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository near_demo
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 8 commits in this repo)...
Contributors loaded, gathering recent usage...
> Starting repository bitcoinmixing
Starting collecting stats...
Simple stats done, starting with contributors (this could take some time with big repos; 5 commits in this repo)...
Contributors loaded, gathering recent usage...
All data loaded, about to sort...

-----------
| Results |
-----------

Overview
--------
Number of commits in project: 24898
Number of commits from upstream (forked project): 0
Number of contributors: 624
Number of branches (Upstream not excluded): 49
Number of tags (Upstream not excluded): 57

Top 6 Contributors (by number of commits)
--------
Author: security-alliance-bot (155511566+security-alliance-bot@users.noreply.github.com)
Number of commits: 13'620
Number of lines added: 49'696
Number of lines deleted: 15'058

Author: H (409H@users.noreply.github.com)
Number of commits: 5'537
Number of lines added: 21'971
Number of lines deleted: 1'300

Author: Nikita Varabei (nVarabei@gmail.com)
Number of commits: 551
Number of lines added: 6'368
Number of lines deleted: 286

Author: Mich (49607867+dubstard@users.noreply.github.com)
Number of commits: 433
Number of lines added: 33'338
Number of lines deleted: 360

Author: AlexHerman1 (38788573+AlexHerman1@users.noreply.github.com)
Number of commits: 377
Number of lines added: 1'417
Number of lines deleted: 161

Author: xiyao (futuretech6@foxmail.com)
Number of commits: 305
Number of lines added: 77'082
Number of lines deleted: 17'348

Top 6 Contributors recently (since 18.04.24) (by number of commits):
--------
Author: cong_wang (congwang@blocksec.com)
Number of commits: 15
Number of lines added: 7'024
Number of lines deleted: 1'385

Author: lwu (lwu@blocksec.com)
Number of commits: 8
Number of lines added: 0
Number of lines deleted: 0

Author: MangoGoing (congwang@blocksec.com)
Number of commits: 2
Number of lines added: 5
Number of lines deleted: 5

Author: Igor Line (igor@line.ee)
Number of commits: 2
Number of lines added: 5
Number of lines deleted: 5

Author: las (48726530+last-las@users.noreply.github.com)
Number of commits: 2
Number of lines added: 2
Number of lines deleted: 1

Author: Yajin Zhou (yajin@vm-kernel.org)
Number of commits: 2
Number of lines added: 3
Number of lines deleted: 5

Top 3 Most Active Repositories
------------------------------
Repository: eth-phishing-detect
Number of commits: 23'926
Number of lines added: 339'347
Number of lines deleted: 41'465
Number of branches: 3
Number of tags: 0

Repository: rustle
Number of commits: 310
Number of lines added: 72'995
Number of lines deleted: 3'083
Number of branches: 3
Number of tags: 5

Repository: solana_demo
Number of commits: 240
Number of lines added: 89'383
Number of lines deleted: 19'374
Number of branches: 3
Number of tags: 0

Warning, the analysed repositories contain empty commits (nothing added or removed). Total empty commits: 106
Done
```