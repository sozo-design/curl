# GitHub Action for curl

Wraps the curl CLI to be used in GitHub Actions. See also [GitHub Action for wget](https://github.com/marketplace/actions/github-action-for-wget).


## Features
 * make http requests
 * http errors are treated as errors


## Usage

### GitHub Actions
```
on: push
jobs:
  curl:
    runs-on: ubuntu-latest
    steps:
    - name: curl
      uses: sozo-design/curl@v1.0.0
      with:
        args: https://httpbin.org/get
```

```
on: push
jobs:
  curl:
    runs-on: ubuntu-latest
    steps:
    - name: curl
      uses: sozo-design/curl@v1.0.0
      with:
        args: -X POST https://httpbin.org/post
```

```
on: push
jobs:
  curl:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: curl
      uses: sozo-design/curl@v1.0.0
      with:
        args: --upload-file .github/workflows/main.yml https://transfer.sh/main-workflow.yml
```

### Docker
```
docker run --rm $(docker build -q .) \
  https://httpbin.org/get
```


## Author
[Clive Walkden](https://github.com/clivewalkden) _clive@sozodesign.co.uk_


## License
[MIT](https://wei.mit-license.org)
