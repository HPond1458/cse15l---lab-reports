# Lab Report 4 - Henry Pond

## Reproducing the Lab 7 Time Trial

### Step 4 - Logging in to ieng6

Keys pressed: `<up><enter>`

The `ssh` login command was the only command I used on my local terminal today, so it was easy to access with the up arrow key.

### Step 5 - Cloning the lab7 fork

Keys pressed: `git<space>clone<space><ctrl+v><enter>`

I copy+pasted the ssh URL from Github into the terminal to speed up this step.

### Step 6 - Running the tests without fixing the bug

Keys pressed: `cd<space>la<tab><enter>bash<space>t<tab><enter>`

I used `<tab>` to auto-complete both commands to save time.

### Step 7 - Fixing the bug with `vim`

Keys pressed: `vim<space>L<tab>.java<enter>20j<enter>5j<enter>4j<enter>5h<enter>r2:wq<enter>`

I used tab to auto-complete the vim command. Vim had saved my place in a different part of `ListExamples.java` from a previous edit.
I jumped down to the line where the bug was by using motion values with `j`, then did the same with `h` to reach the character I needed to change.
I then used the `r` command to replace 1 with 2, then saved my changes and exited vim with `:wq`.

### Step 8 - Running the tests after fixing the bug

Keys pressed: `bash<space>t<tab><enter>`

I repeated exactly what I did in step 6, and this time the tests succeed.

### Step 9 - Committing and pushing the results to Github

Keys pressed: `git<space>add<space>.<enter>git<space>commit<space>-m<space>"Fixed<space>bug<space>in<space>ListExamples.java"<enter>git<space>push<enter>`

I ran the `git` commands as we did in the week 4 lab. However, I ran into fewer issues this time because of the SSH keys I set up.
