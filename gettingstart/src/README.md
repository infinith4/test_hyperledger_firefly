curl -OL https://github.com/hyperledger/firefly-cli/releases/download/v1.3.1/firefly-cli_1.3.1_Linux_386.tar.gz

sudo tar -zxf ./firefly-cli_*.tar.gz -C /usr/local/bin ff && rm ./firefly-cli_*.tar.gz

ff version


ff init fabric

stack name: dev


Your docker compose file for this stack can be found at: /home/vscode/.firefly/stacks/dev/docker-compose.yml

オプションが見れる

```
ff init ethereum --help
ff init fabric --help
```

ff start dev

