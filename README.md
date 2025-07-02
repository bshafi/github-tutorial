# Github Tutorial

## 1. Setup Python
https://realpython.com/installing-python/

## 2. Setup Github
https://docs.github.com/en/get-started/git-basics/set-up-git


## 3. Clone this Repo
```
git clone https://github.com/bshafi/github-tutorial.git
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

## 4. Basic Git Flow

![img](resources/git%20flow.svg)

1. Create a file in the called `example1.py` and add `print("Hello World")` to the file.
2. Run `git add example1.py`
3. `git commit -m "added example for tutorial"`
4. `git push`