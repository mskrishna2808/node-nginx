# node-nginx

To install docker compose

```
sudo curl -L https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose

docker-compose version
```

Create a Secret for JFROG username and password in plain text

```
{
  "username" : "privateRegistryUsername",
  "password" : "privateRegistryPassword"
}

```

Add below line into Container definition file

```
    "repositoryCredentials": {
      "credentialsParameter": "arn:aws:secretsmanager:region:aws_account_id:secret:secret_name"
    },

```

For ECS task execution role add below inline policy to access secrets manager

```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "ssm:GetParameters",
                "secretsmanager:GetSecretValue"
            ],
            "Resource": [
                "arn:aws:secretsmanager:region:aws_account_id:secret:secret_name"
            ]
        }
    ]
}

```