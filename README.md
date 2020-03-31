# vscode-in-docker by Casthash532

This will explain on how we use [Docker](https://www.docker.com/) to setup a productive local development environment quite easily.

try it out:  

### 1- install vscode locally:
```bash
  cd /bin && \
	sudo wget https://github.com/cdr/code-server/releases/download/2.1698/code-server2.1698-vsc1.41.1-linux-x86_64.tar.gz && \
	sudo tar -xvzf code-server2.1698-vsc1.41.1-linux-x86_64.tar.gz && \
	sudo rm -r code-server2.1698-vsc1.41.1-linux-x86_64.tar.gz && \
	sudo mv code-server2.1698-vsc1.41.1-linux-x86_64/ vscode/ && \
	cd /home
```

### 2- run a container with vscode mounted in:
```bash
  docker run --privileged \
            -p 127.0.0.1:8080:8080 `#change external port 127.0.0.1:xxxx:8080 for multiple environements` \
            -v "$PWD:/home" \
            -v "/bin/vscode:/bin/vscode" \
            -it `#Environement:php,node,python...`   /bin/vscode/code-server --auth none
```

### 3- Open port '8080' (or xxxx) on your browser


           
