
# Centralized workflow exercise

In this exercise, we practice collaborative centralized workflow.
First, we all **clone** (make a local copy) and try to **push** (send
code to) the main repository.  We'll see a small problem with that,
and then make a **pull request** (sending code so that others can
review and accept later).  We'll discuss how this leads to code review
and discuss a number of typical pitfalls.

Please don't go too far ahead, because we will learn from problems
that come up.

## Before we start

Everyone needs their GitHub account to be added to our central repository.

1. Participants add their usernames to a shared document.
2. Instructor adds participants as collaborators to this project.


## After participants have been added as collaborators


### 1. Clone this repository


### 2. Step into the newly created directory

```
$ cd centralized-workflow-exercise
```


### 3. Create a file with a unique name, e.g.: `yourusername.txt`

In this file share your favourite cooking recipe or haiku or Git trick or whatever.


### 4. Stage and commit the change

```
$ git add yourusername.txt
$ git commit
```


### 5. Try to push the change to the upstream repository

```
$ git push origin master
```

By **"upstream"** we mean here the repository which we have cloned.
Imagine "upstream" being closer to the main development and your local
clone to be "downstream".


### 6. **Stop here** and discuss why push for most participants was rejected

You probably see something like this:

```shell
$ git push
To https://github.com/user/repo.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'https://github.com/user/repo.git'
To prevent you from losing history, non-fast-forward updates were rejected
Merge the remote changes (e.g. 'git pull') before pushing again.  See the
'Note about fast-forwards' section of 'git push --help' for details.
```

The push only worked for one participant. Why?

The natural reflex is now to `git pull` first but
what happens if we `git pull origin master`?


### 7. Pull updates from the upstream repository

```
$ git pull origin master
```


### 8. **Stop here** and discuss why we obtained a merge commit locally

Ideas? What happened under the hood? Discuss `git fetch` as an alternative to `git pull`.
Discuss `git pull --rebase` as an alternative to avoid merge commits.


### 9. Try to push again

It will work for one more person.


### 10. Create a branch `yourname/somefeature` pointing at your commit

First find out the hash of your commit. You can do this using `git graph` or `git log`:

```
$ git log yourusername.txt
```

Then create a branch "in the past" pointing to that hash:

```
$ git branch yourname/somefeature [hash]
```

The `yourname/` prefix has no special meaning: it is just part of a
branch name to indicate who made it.


### 11. Push your change as a new branch

```
$ git push origin -u yourname/somefeature
```

Can we leave out the `-u`?


### 12. Submit a pull request

Submit a pull request from your branch towards the `master` branch.
Do this through the web interface.

Finally also discuss {{ site.centralized_workflow_exercise_url }}/network.
