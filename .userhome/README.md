# Convienence settings


# Setup for Kubernetes
https://kubernetes.io/docs/reference/kubectl/quick-reference/

Add the following to ~/.zshrc
```zsh
# kubectl autocompletion
alias k='kubectl'

autoload -Uz compinit
compinit
source <(kubectl completion zsh)
```