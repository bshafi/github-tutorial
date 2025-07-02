# Github Tutorial

## Setup Python
https://realpython.com/installing-python/#step-1-download-the-official-python-installer

Use this to ensure python was correctly installed
```
  python --version
```

## Setup Github
https://github.com/git-guides/install-git


Type this and if you get usage
```
  git
```

https://docs.github.com/en/github-cli/github-cli/quickstart

```
  gh auth login
```


## Clone this Repo
```
git clone https://github.com/bshafi/github-tutorial.git
```

Go into that directory
```
cd github-tutorial
```

## Enable Running Scripts on Windows
If you can't run scripts use this in a admin powershell
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

## Setup Virtual Environment and Install Requirements
```
python -m venv .venv

# On Windows
.\.venv\Scripts\activate

# On Mac and Linux
source .venv/bin/activate
```
Install all the necessary python libraries
```
python -m pip install -r requirements.txt
```

## Basic Git Flow

![img](resources/git%20flow.svg)

1. Create a file in the called `example1.py` and add `print("Hello World")` to the file.
2. `git add example1.py`
3. `git status`
3. `git commit -m "added example for tutorial"`
4. `git push`

When you are working in production environment you don't create a commit for a single line of code. This is just for this tutorial.

Now add 4 new print statements to the `example1.py` file. Create a new commit for each line. Make sure to create a different commit message.

## Retrieving Updates

Git is made for collaboration so other programmers may work on a piece of code and add it. Whenever you start working make sure to run `git pull` to get all the updates to the code.

```
    git pull
```

## Branching

The main reason we use Git instead of other tools like DropBox and Google Drive is that it allows programmers to collaborate. If one programmer is in the middle of typing out their code and another developer is testing their code it will create a bunch of errors. 

The way we do this is called branching. Before we start creating any code we create a `branch`. This `branch` is an exact copy of the code that can't be changed by others. Once we've added our feature or fixed a bug, we `merge` the branch back into the `main` branch.

Let's redo the first steps of this tutorial with branching.

```git checkout -b example2```

This creates a branch called `example2` of off the current branch which is called the `main` branch. 

Run this command:

```git branch```

You should see:

```
  main
* example2
```

This shows the two branches `main` and `example2`. The `*` indicates that we are currently on the `example2` branch. Go back to the main branch by using `git checkout main` and return back to example2 using `git checkout example2` (Note that there is no `-b` in this command).

Now redo the same steps as example1 but use `example2.py` instead. You'll notice that something strange happens when you try to push. Git will tell you to use a different command.

We've made a lot of changes to the branch `example2` however if you take a look at the github page none of them are appearing. How do we get the changes to `example2` to the `main`?

Take a look at the top of this github page you should see `Create Pull Request`. Click on that link

## Pull Requests

You should be on a screen with `Open a Pull Request`. Type a example description and 

Pull requests are the way you request your changes to be added to the code base. Then the maintainers of the code base will review your changes and if they accept the changes they will merge it into the codebase.