# OpenSSH Cheat-Sheet

## SSH Keys

### Generate ssh keypair
This keypair will be placed in ~/.ssh/ by default. Two files will be created: id_rsa (private key) and id_rsa.pub (public key).
```shell
ssh-keygen
```
> [!warning]
> Do not share your private key with anyone!

### Copy public key to server
Copy the public key to any server you want to ssh into.
```shell
scp .ssh/id_rsa.pub user@server:~/id_rsa.pub
```
On the server, cat the public key's content to .ssh/autohrized_keys.
```shell
cat id_rsa.pub > .ssh/authorized_keys
```

## Known Hosts

Remove Entry from the Known-Hosts File.
```bash
ssh-keygen -R hostname
```

## Using the SSH Config File
If you are regularly connecting to multiple remote systems over SSH, you can configure your remote servers with the `.ssh/config` file.

**Example:***
```ini
Host dev
    HostName dev.your-domain
    User xcad
	Port 7654
    IdentityFile ~/.ssh/targaryen.key

Host *
    User root
    Compression yes
```

Connect to a host (like *dev* , eg.) with `ssh dev`.
