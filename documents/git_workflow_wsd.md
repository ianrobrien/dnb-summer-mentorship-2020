title Git workflow

participant "working directory"
participant "staging"
participant "local"
participant "remote"

remote->working directory: git clone
remote->local: git fetch
remote->working directory: git pull
local->working directory: start editing
working directory->staging: git add
staging->local: git commit
local->remote: git push

