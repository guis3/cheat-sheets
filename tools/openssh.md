# OpenSSH Cheat-Sheet

## SSH Keys

### Generate SSH Keypair

This keypair will be placed in `~/.ssh/` by default. Two files will be created: `id_rsa` is the private key and `id_rsa.pub` is the public key.

```shell
ssh-keygen
```

> [!warning]
> Do not share your private key!

### Copy Public Key to Server

Copy the public key to any server you want to ssh into.

```shell
ssh-copy-id user@hostname
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
Host web
    HostName web.gui.local
    User gui
	Port 22
    IdentityFile ~/.ssh/id_rsa

Host *
    User root
    Compression yes
```

Connect to a host (like *web* , eg.) with `ssh web`.
