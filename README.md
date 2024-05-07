# Get Job ID Action

GitHub doesn't provide the job id anywhere so here's a simple action to get the job id for the current job.

## Usage

Calling the action in the job you want to get the job id for. Provide an ID for the step so you can reference the output.

#### Example
```yml
jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: austenstone/job-id@v1
        id: job-id
      - run: echo $GITHUB_JOB_ID
        env:
          GITHUB_JOB_ID: ${{ steps.job-id.outputs.job-id }}
```

## ➡️ Inputs
Various inputs are defined in [`action.yml`](action.yml):

| Name | Description | Default |
| --- | - | - |
| github&#x2011;token | Token to use to authorize. | ${{&nbsp;github.token&nbsp;}} |


## ⬅️ Outputs
| Name | Description |
| --- | - |
| job-id | The job id for the current job. |

## Further help
To get more help on the Actions see [documentation](https://docs.github.com/en/actions).
