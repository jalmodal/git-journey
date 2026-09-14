# Remote
Before we can push anything up to Github, we need to tell Git about our remote repository on Github. We need to setup a "destination" to push to.

In Git, we refer to these "destinations" as remotes. Each remote is simply a URL where a hosted repository lives.

## Viewing Remotes
To view any existing remotes for your repository, we can run `git remote` or `git remote -v` (verbose)

This just displays a list of remotes. If you haven't added any remotes yet, you won't see anything.

## Adding A New Remote
A remote is really two things: a URL and a label.  
To add a new remote, we need to provide both to Git.

`git remote add <name> <url>`

example: `git remote add origin https://github.com/repo/repo.git`

### Origin?
Is a conventional Git remote name, but it is not at all special. It's just a name for a URL.

When we clone a Github repo, the default remote name setup for us is called origin. You can change it. Most people leave it.

## Other commands
They are not commonly used, but there are commands to rename and delate remotes if needed.

- `git remote rename <old> <new>`
- `git remote remove <name>`
