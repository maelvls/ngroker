## Install `ngroker` on Linux

An sshd deamon must be running. Things required in your PATH: [ngrok](https://ngrok.com/download), [jl](https://github.com/koenbollen/jl), [tmux](https://github.com/tmux/tmux/wiki/Installing), [jq](https://stedolan.github.io/jq/download/)

## Install `ngroker` on macOS

(1) Make sure `sshd` is running (go to  → System Preferences → Sharing → check the box "Remote login")

(2) Install `ngroker` by running the following commands:

```sh
brew install jq tmux koenbollen/public/jl
brew cask install ngrok
curl -L https://gist.githubusercontent.com/maelvls/d0b34b23dfafeabc2b23b710e413f5ea/raw/b95c2c045f63c8fec1ec5d63c82809273a14f04b/ngroker > /tmp/ngroker && install /tmp/ngroker /usr/local/bin
```

(2) Then, make sure you are [registered with ngrok](https://dashboard.ngrok.com/get-started/setup) (e.g. using your Github account to signup/log in)

(3) Copy the `authtoken` in the [ngrok setup page](https://dashboard.ngrok.com/get-started/setup) and run:

```sh
ngrok authtoken <the-token-displayed-in-get-started-setup>
```

## Use `ngroker` to share a tmux session with a colleague

Finally you can create a session someone by giving their Github
username (e.g. `maelvls`). The session will happen in `tmux attach -t
ngroker`

```sh
# Share session with mael
ngroker maelvls

# Let's be crazy and share the session with two people!
ngroker maelvls Callisto13
```

Demo:

![act](https://user-images.githubusercontent.com/2195781/85836295-b05bb900-b796-11ea-9565-9099a3d4b018.gif)