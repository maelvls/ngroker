(1) Install `ngroker` on macOS (it's just a tiny bash script, see below):
```sh
brew install koenbollen/public/jl
brew cask install ngrok
brew install jq
curl -L https://gist.githubusercontent.com/maelvls/d0b34b23dfafeabc2b23b710e413f5ea/raw/6b177aa7e0808d5e1843ef4f446822e5b7bc334e/ngroker > /tmp/ngroker && install /tmp/ngroker /usr/local/bin
```

(2) Then, make sure you are [registered with ngrok](https://dashboard.ngrok.com/get-started/setup) (e.g. using your Github account to signup/log in)

(3) Copy the `authtoken` in the [ngrok setup page](https://dashboard.ngrok.com/get-started/setup) and run:

```
ngrok authtoken <the-token-displayed-in-get-started-setup>
```

(4) Finally you can create a session with e.g. `maelvls` (or any other Github username). The session will happen in `tmux attach ngroker`

```
ngroker maelvls
```
