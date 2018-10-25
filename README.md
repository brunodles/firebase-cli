# FirebaseCLI
Firebase CLI packaged on alpine linux container

## Usage
The simplest way to use is just call this line below.

```bash
docker run -it -v \"$(pwd):/home/node/app\" -v \"$HOME/.config:/home/node/.config\" -w \"/home/node/app\" --user=node -p 9005:9005 -p 5000:5000 node_firebase sh"
```
This command will:
* Run docker on interative mode
* Create a volume linking `current directory` with `/home/node/app`
* Create another volume linking `HOME/.config` and `/home/node/app`, this will be used to keep your data after loging inside docker container. It can also be replaced to another place, if you like or removed.
* Set docker to use node user
* Foward calls on ports 9005 and 5000 to container
* Open a shell inside container


### Alias
Another way to use, is to create a alias.

Just add it on `~/.bashrc` or `~/.zshrc` and call it as it was installed:
```bash
alias firebase="mkdir $HOME/.config >/dev/null 2>&1 || docker run -it -v \"$(pwd):/home/node/app\" -v \"$HOME/.config:/home/node/.config\" -w \"/home/node/app\" --user=node -p 9005:9005 -p 5000:5000 node_firebase firebase"
```
