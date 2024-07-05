## Local Development

### Environment Setup
* Clone this repository
* Initialize your virtual environment ([Guide](https://www.newline.co/courses/create-a-serverless-slackbot-with-aws-lambda-and-python/installing-python-3-and-pyenv-on-macos-windows-and-linux))
  * `python -m venv .venv`
* Activate environment: 
  * `source .venv/bin/activate`
* Install Poetry and the project dependencies:
  * `pip install poetry`
  * `poetry install`

### Meltano Initial Setup
* Install extractor:
  * `meltano install extractor tap-github`
* Install loaders:
  * `meltano install loader target-jsonl`
  * `meltano install loader target-csv`

### Create Github Token
* Visit the [Github tokens page](https://github.com/settings/tokens?type=beta)
* Click on the "Generate New Token" button
* Give it a name, expiration, and permissions to access public repositories only
* Click on "Generate Token"
* Copy the token and add it to a .env file
  * `TAP_GITHUB_AUTH_TOKEN=token`
* Alternatively, export it to the terminal
  * export TAP_GITHUB_AUTH_TOKEN=token

### Run it!
* Run the following command
  * `meltano run tap-github target-jsonl`
* Feel free to modify the meltano.yml in the "select" to modify what to extract