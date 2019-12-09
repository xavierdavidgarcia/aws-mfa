
### Install
Download the binary
* copy the binary to /usr/local/bin <---- be sure this path is on your PATH
* rename it aws-mfa if it's darwing version

### Configure AWS:

Go to you ~/.aws/credentials and edit it

Example with staging.
* Rename staging on staging-default
* Copy/past all section and remove the secrets
* rename the new one staging
* add the section aws_session_token

``` 
[staging-default]
aws_access_key_id     = AKI$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
aws_secret_access_key = $$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$
region                = us-west-2
output                = json

[staging]
aws_access_key_id     = 
aws_secret_access_key = 
aws_session_token     = 
region                = us-west-2
output                = json
```

Save your new file

### Usage:

```bash
╭─xgarcia@x1 ~/Development/01-Eureka/gospace/src/github.com/xavierdavidgarcia/aws-mfa  
╰─➤  ./aws-mfa --help
Usage of ./aws-mfa:
  -d string
    	Aws default profile (default "default")
  -m string
    	Aws MFA enabled profile (default "mfa")
```

### How to update your auth token:
```
root@loclahost# # aws-mfa -s staging-default -d staging
Using device arn:aws:iam::account-aws-id:mfa/xgarcia
Enter MFA code: 1234546

```
