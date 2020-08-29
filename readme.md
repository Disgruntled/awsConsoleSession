# AWS Console Session tool

A really basic script which is a modification of some AWS code to allow you to do to take the credentials of an assumed IAM role (Access Key, Secret Access Key, Session Token) and use them to generate a link to the AWS console allowing you to use the console as that role.

The script has some basic error checking, a few different different modes of operation. It can read AWS credentials from the OS environment, a specified credential file/profile, or from the meta data endpoint.

## Invocation

The script "consoleSession.py" will take the AWS access key/secret access key/session tokena and use them to create a url you can use for the AWS console.

It will attempt to read the access key pair+session token from environment variables, then ~.aws/credentials default profile if nothing exists in the environment.

This can be overriden with arguments -c to specify a credfile, and -p for a profile

--metadata is a neat flag that tries to get credentials from the metadata endpoint. It allows you to use the AWS console as an EC2 instance.


```bash
python3 consoleSession.py -c "path/to/credentials/file" -p "profile"
```

or

```bash
python3 consoleSession.py
```

or

```bash
python3 consoleSession.py --metadata
```

## Dependencies

see requirements.txt

```bash
pip3 install -r requirements.txt
```
