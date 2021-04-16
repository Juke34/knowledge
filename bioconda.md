## Commands
I never succeded to make the bioconda suggested command work:  
`bioconda-utils build --git-range master`

I use instead:  
`bioconda-utils build recipes/ config.yml  --packages agat`


I never succeded to make the bioconda suggested command work:  
`bioconda-utils build --docker --mulled-test --git-range master`

I use instead:  
`bioconda-utils build --docker --mulled-test --package agat`


## Errors
I got the following error:  
`conda.exceptions.InvalidVersionSpec: Invalid version '>=5.8': invalid character(s)`

I succeeded to pass over using:  
`conda upgrade -n base conda`
