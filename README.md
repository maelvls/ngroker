![act](https://user-images.githubusercontent.com/2195781/85836295-b05bb900-b796-11ea-9565-9099a3d4b018.gif)

## Install `ngroker` on Linux

Required:
1. some binaries in your PATH + `sshd` instance running:
   [ngrok](https://ngrok.com/download), [jl](https://github.com/koenbollen/jl),
   [tmux](https://github.com/tmux/tmux/wiki/Installing),
   [jq](https://stedolan.github.io/jq/download/);
   to install all that, run:

   ```sh
   sudo apt install openssh-server tmux jq snapd
   sudo snap install ngrok
   go get github.com/koenbollen/jl
   ```
  
2. the `ngroker` script somewhere in your PATH, e.g.:

   ```sh
   curl -sL https://raw.githubusercontent.com/maelvls/ngroker/master/ngroker > /tmp/ngroker
   install /tmp/ngroker $(go env GOPATH)/bin
   ```

## Install `ngroker` on macOS

(1) Make sure `sshd` is running (go to  → System Preferences → Sharing → check the box "Remote login")

(2) Install `ngroker` by running the following commands:

```sh
brew install jq tmux koenbollen/public/jl
brew cask install ngrok
curl -sL https://raw.githubusercontent.com/maelvls/ngroker/master/ngroker > /tmp/ngroker
install /tmp/ngroker /usr/local/bin
```

(2) Then, make sure you are [registered with ngrok](https://dashboard.ngrok.com/get-started/setup) (e.g. using your Github account to signup/log in)

(3) Copy the `authtoken` in the [ngrok setup page](https://dashboard.ngrok.com/get-started/setup) and run:

```sh
ngrok authtoken <the-token-displayed-in-get-started-setup>
```

## Use `ngroker` to share a tmux session with a colleague

Finally you can create a session someone by giving the script their Github
username (e.g. `maelvls`). The session will happen in `tmux attach -t
ngroker`

```sh
# Share session with mael
ngroker maelvls

# Let's be crazy and share the session with two people!
ngroker maelvls Callisto13
```


## FAQ

```sh
% ssh jack@0.tcp.eu.ngrok.io -p 15597
kex_exchange_identification: Connection closed by remote host
```
that means sshd isn't running on the machine that runs `ngroker`
