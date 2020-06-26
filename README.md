(1) Install `ngroker` on macOS (it's just a tiny bash script, see below):

```sh
brew install koenbollen/public/jl
brew cask install ngrok
brew install jq
curl -L https://gist.githubusercontent.com/maelvls/d0b34b23dfafeabc2b23b710e413f5ea/raw/dc899bd78fdd9a247a193cd693e1301f17d045b3/ngroker > /tmp/ngroker && install /tmp/ngroker /usr/local/bin
```

(2) Then, make sure you are [registered with ngrok](https://dashboard.ngrok.com/get-started/setup) (e.g. using your Github account to signup/log in)

(3) Copy the `authtoken` in the [ngrok setup page](https://dashboard.ngrok.com/get-started/setup) and run:

```sh
ngrok authtoken <the-token-displayed-in-get-started-setup>
```

(4) Finally you can create a session with e.g. `maelvls` (or any other Github username). The session will happen in `tmux attach -t ngroker`

```sh
ngroker maelvls
```
