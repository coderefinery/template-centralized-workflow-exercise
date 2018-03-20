
# Centralized workflow exercise

Exercise to practice collaborative centralized workflow. On the way to a pull request
and code review we will meet and discuss a number of typical pitfalls.


## Before we start

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

By "upstream" we mean here the repository which we have cloned.
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

It will work only for one participant. Why?

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

First find out the hash of your commit, then create a branch "in the past" pointing to that
hash:

```
$ git branch yourname/somefeature [hash]
```


### 11. Push your change as a new branch

```
$ git push origin -u yourname/somefeature
```

Can we leave out the `-u`?


### 12. Submit a pull request

Submit a pull request from your branch towards the `master` branch.
Do this through the web interface.

Finally also discuss {{ site.centralized_workflow_exercise_url }}/network.
