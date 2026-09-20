## Examples


```
name: print-name

on:
  push:
    branches:
      - main

jobs:
  print-message:
    runs-on: ubuntu-latest
    steps:
      - name: Print a message
        run: echo "Hello from GitHub Actions! The workflow ran successfully."
```

```
name: manual-workflow

on:
  workflow_dispatch:
    inputs:
      environment:
        description: "Target environment"
        required: false
        default: "dev"
        type: string
      version:
        description: "Version to deploy"
        required: true
        type: string

jobs:
  manual-job:
    runs-on: ubuntu-latest
    steps:
      - name: Print input values
        run: |
          echo "Environment: ${{ inputs.environment }}"
          echo "Version: ${{ inputs.version }}"
```
