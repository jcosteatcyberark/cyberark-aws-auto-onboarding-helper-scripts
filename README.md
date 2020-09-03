# Helper scripts - CyberArk Auto Onboarding Lambda

## Introduction

This project is a collection of scripts to help deploy the [CyberArk Auto Onboarding Lambda](https://github.com/cyberark/cyberark-aws-auto-onboarding).

```
.
├── build             # Build the lambda sources as ZIP files (using Docker)
├── configure         # Create a parameters.json file used to deploy the project
├── delete            # Delete the stack and stack-set from AWS
├── deploy            # Deploy the stack and stack-set
├── docker            # Docker files used to build the zip files (see ./build) 
├── sync              # Sync the lambdas source code on S3
└── utils             # Library of useful functions
```

## Prerequisites
 - Docker (to build the sources)
 - Bash
 - AWS cli (logged in)

## Usage

Run the scripts in the following order:
```
# Build an image named aws_onboarding_lambda_builder and run it.
$ bin/build

# Zip sources should now be in dist/lambdas. Sync them to the S3 buckets
$ bin/sync

# Configure the stack parameters. A parameters.json file will be generated.
$ bin/configure

# Deploy the required stack and stack-set on AWS
$ bin/deploy

# Optional: Delete the stack and stack-set
$ bin/delete
```

## Licensing

Copyright © 2020 CyberArk Software Ltd

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.