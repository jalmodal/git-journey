# Cloning
So far we've created our own Git repositories from scratch, but often we want to get a **local copy of an existing repository** instead.

To do this, we can clone a remote repository hosted on Github or similar websites. All we need is a URL that can tell Git to clone for use.

To clone a repo, simply run `git clone url`.

Git will retrieve all the files associated with the repository and will copy them to your local machine.

In addition, Git initializes a new repository on your machine, giving you access to the full Git history of the cloned project.

> Make sure you are not inside of a repo when you clone!

### SSH (Secure Shell Protocol) Config
You need to be authenticated on Github to do certain operations, like pushing up code from your local machine. Your terminal will prompt you every single time for your Github email and password, unless...

You generate and configure an SSH key. Once configured, you can connect to Github without having to supply your username/password.

1. To check if existing SSH keys are present enter `ls -al ~/.ssh` on git bash.
2. To generate a new key `ssh-keygen -t ed25519 -C "your_email@example.com"`
3. Visit [Github](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh) for detailed instructions.