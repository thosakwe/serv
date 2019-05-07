# serv
Tool for producing reproducible server configuration.

## Why?
Many Web applications will eventually grow past the point where they can be
supported by just one server. However, running the same application on
multiple, *different* servers can cause unforeseen problems.

`serv` aims to make it easy to run shell scripts on multiple systems, while
also ensuring that they all remain identical.

## Notes
* All commands are reversible, by design.
* Commands are run like database transactions. One failure reverts the entire
current batch.
* `serv` diffs files to see if the configuration has changed. If so, only
new commands are executed. If lines containing previously-executed commands
changed, then the changes are rejected. This way, server integrity can be
guaranteed.

## Planned
* `serv` daemon - allows sync via network
* `lxc` support
