# gitlab-issue-import

Good enought script to import Gitlab issues when you can not generate an access token to use other import tools. The `issue.csv` file is downloaded from Gitlab. Labels and Milestones are based on copy and paste, where fields are seperated by `,`. Make sure your fields do not contain unnecessary leading and tailing spaces.
Test the script on a dummy repo frist!

Python script is using [Jupyter Notebook](https://jupyter.org/)

Install the following libraries
````
pip install pandas
pip install PyGithub
````

## How to use it

- Insert your github token
- Modify the user lookup table in cell 5 `githubUsers`. Every contributer **with** a github account should be represented.
- Change to your repo in cell 6
- Cell 7 & 8 import non existing labels and milestones. Milestones are stored in a lookup table to reference in issues.
- Cell 9 is the issue import. Every importet issue will be printed. The script then pauses for 15 seconds to avoid timeouts from github. This script will import ~150 issues and will throw a secondary rate limit timeout. Remove the importet rows, reimport the file in cell 3 and wait for 30-60 minutes and start the import again. Repeat until finished.. not ideal, but good enough.
- fingers crossed you never have to import issues from gitlab without access tokens on private projects 🤞