# Hipo feature planning

Hipo is a self-hosted documentation server with a text user interface (TUI) for use in the command line environment. It is built on a number of already existing open source libraries, such as:

- Wish
- Bubble Tea
- webhook
- ssh

The primary use case for Hipo is to serve internal documentation to technical teams who already use a terminal as part of their daily work and are interested in building in webhook push/poll actions to their documentation, and want to control access to their documentation with SSH keys. 

Hipo acts as a git remote for repositories containing markdown files. Each markdown file acts as a 'scene' or section of the documentation. Each scene can contain 0 or 1 webhook actions to be triggered. 

Templates are used to add interactivity to the scenes, such as links to other scenes, styling features, and plugin functionality.

## v0.1.0 (current)

- DONE Rename the repo to hipodocs before pushing any features.

Proof of concept features:

- server
  - middleware
    - wish: helpers to create ssh apps
    - ssh server: ssh helpers for wish
    - wish git middleware: hipo will read markdown from git repos which can be handled like any other git repo
    - wish logging middleware: gotta log
    - wish bubbletea middleware: to serve the TUI
  - cmd
    - start command to start server
- config
  - config struct: server config
  - user struct: users have access to repos and the server
  - repo struct: git repos 
  - NewConfig struct: generate a new config from a repo/user/config 
- git
  - repo: base repo functions
  - errors: error handling functions
  - commit: commit functions
  - reference: ref functions
  - tree: tree functions
- ui
  - components: bubble tea app components
  - styles: style/theming
- main