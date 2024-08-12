# Clickdown

A single file script for Issue management. Just `clickdown init` and read the README.md if you want to get deeper.

## Features

* Create tickets
* Create boards
* Powerful ticket template language capable of any possible ticket customization
* Powerful search by any attribute and efficient full-text search
* Powerful history, even displaying ticket changes per-line!
* Extremely easy to setup and get started

## Dependencies

`git`, `grep` (optional), `sh`

## Suggested flow

If you're coming from traditional extremely overloaded project management software
(like Jira or Clickup), it might be a little confusing how everything related to
ticket management was already there. Please refer to the following recepies.

### Create a project

Create a new empty directory, enter it and run `clickdown init`.
It will create Git repository, ticket template file and a README.
Then you'll need to configure git by editing `.git/config` to put
the project files on some git hosting (like Github, Gitlab or sr.ht).

### Use existing project

Just use `git clone` with a URL of the project you want to use

### Create a ticket

Just run a `clickdown new Ticket` and it will create an empty ticket with
a name Ticket and some ither fields. Each field is populated by a simple shell command.

### Edit a ticket

Just call `clickdown edit Ticket` and it will edit a ticket and push
it with relevant commit message

### Edit a ticket template

Ticket template is just a shell template which allows regular shell commands
to be executed inside of the `$()`. To edit it, call `clickdown edit-template`

### Create a sprint or workflow or ticket group.

Simply create a directory like `mkdir Sprint-1`. To put some tickets there, use symbolic links,
like `ln -s ticket/Learn_Clickdown.txt Sprint-1`. To document what this sprint is about, just
put a file called `README.md` in the directory.

> Don't forget to commit and push the change with `git add . && git commit -m "Added Sprint-1" && git push`

### Search tickets

To search by any field, use a powerful utility called `grep`. For example, to search by author use
`grep "Author: Jhon Doe" tickets/*`. To search tickets by status (if you have this field), use
`grep "Status: OPEN" tickets/*`. To search in specific sprint or workflow or ticket group, use
`grep "Author: Jhon Doe" Sprint-1/*`

### View history

For history and synchronization, clickdown uses powerful `git` utility. To view history of changes
for specific ticket, use `git blame tickets/Ticket.txt`. To view history of all changes
in the project, use `git log`

### Web user interface

Sometimes you don't have access to CLI. In this case, feel free to use powerful and extremely
efficient interfaces or your Git hosting

## Special thanks

To Clickup, for loading the sprint board for soo long, that I was able to write this whole project from scratch.
