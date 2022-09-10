# When you make a mistale


This document has recommendations for when you made a mistake:

[You pushed your mistake to the shared repo](#shared)
[You added a junk file and only added it, but did not commit](#added)
[You changed stuff, but did not want to commit it](#not_adding)

### Shared your mistake
#### shared

You went all the way and pushed a mistake up to the shared repo. Don't worry. You can rewind, just do it as soon as possible. `git log` will show you your last commits with an id has. `git revert <commit_id>` will roll the changes back on to the step you put in the commit_id for locally. Now just push your local changes again. 


### You added incorrect files but did not commit your mistake
#### added

You just added a bunch of stuff you should not have. No worries! Just remove them (like go to the local files on your machines and move them away) then go `git status` and start the cycle again.    


### You changed files but did not want commit your tinkering
#### not_adding

You just modified a bunch of stuff and you should not have the modifications up on the main repo. When you type `git status` you see this and you want to go back. No worries, just `git restore <file_name>`



