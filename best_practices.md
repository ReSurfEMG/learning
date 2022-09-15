# Best practices :trophy:


This document could also have been titled 'how to work well with others, through Python code.' The truth is that that coding, whether in Python or any other language, is very similar to writing. There are a lot of ways to say things and get your point across, but some more way elegant than others. It actually matters less if you are elegant, than if others (both people and computers) can understand you at all. Unfortunately, there are a few mistakes that can make understanding very difficult or even impossible.
Therefore, a few recommendations:


### Pep-8 check :8ball:

Pep-8 (https://peps.python.org/pep-0008/) is the way to make sure your code is in line with standards. You can get any one of a variety of tools to help you fix formatting mistakes. In any package I build since 2022 you can run a lint easily, and the CI will have a lint checker. What is impossible to automate is using the proper convention in terms of how classes versus functions are called. Classes have caps, functions do not. If you want what you write to make sense to everyone keep your code in line with conventions. In extreme cases your code will do something different than you programmed it to just because the formatting is incorrect.


### When in doubt, comment :pencil2:

If there is any part of your work that would not be obvious, explain it in the comments. If in doubt about whether it is obvious, just add comments. We can take them out easily, but if we don't know what you intended, we can't put them in for you.


### Name your folders :file_folder: and files without spaces 

Eventually, you will want to do something in command line or with some other method that only deals well with things with sensible names. I know your folder entitled 'I don't care about my data' has a perfectly sensible name in your eyes, but for command line that is at a minimum 6 different variables, assuming you know how to write a special character to get the "'" in there. If you want such a long name it should be 'I_do_not_care_about_my_data' . The same goes for file names and all variables. Keep all names and variables space free. 


### Keep your notebooks :notebook: cleaned out

The most proper way to add notebook on shahred repository is to clear the kernel, run the notebook from top top bottom, then clear the whole thing out again. This means no outputs are sent to the shared repository. We have left some notebooks before the last stage as we think community members may benefit. In no circumststances should you ever commit a notebook in an intermediate state (you ran some of the cells out of order). Because variables are kept saved, this inevitably shows erroneous results. 


### One issue, one commit, one push :one:

If you have a lot of work it's tempting to do it all, and then add, commit and push it. Or just commit and push whenever you are afraid you need to save stuff. This is the wrong approach. Remember you may have to roll back out of your work at some point, so if your push had changes to 3 different files, it's harder in case just one thing is wrong. Solve an issue, add, commit, push, then repeat. 


### Stay off the main branch, open your own

There is one main branch, and the bigger a project gets, the more you should stay off it, always. The proper way to change things is open your own fork (or branch if you are an invited to), change things there, then put in a pull request. This is much better for other people who have expectations that the main branch is fairly stable, and won't have an accidental bug popping up every other commit. In theory you could play on the main branch, and never push it back. In reality things never work that way for long. It's customary to open a branch with your github username and then '/exploring' to play around. If you then want to catch your branch up to changes on the main, rebase it.


### Even off the main branch, stay out of areas others are working on

If you see someone is working on a specific function (check the project board), now is not the time to write your own version of it named exactly the same thing. Wait until they finish, then rebase your fork or branch on their work after it has been pulled to the main branch. If you just can't wait, then use common sense and rename your function something else. If person A works on lines 30 to 40, and person B works on lines 30 to 40, and they both continually update the code at the same time, they will do twice the work to get less than half the results. Always check the project board, and communicate with others.   


### Never hard-code a path

If you are working by yourself on a file no one else needs, hard-code your paths for convenience. A hard coded path is something like this: "C:/Projects/my_project96/neverland/data/M004/009/". Fine for messing around at home along but the moment you start working with others, this makes problems. Both [ReSurfEMG](https://github.com/ReSurfEMG/ReSurfEMG) and [eegyolk](https://github.com/eegyolk-ai/eegyolk) libraries now have examples where hard coded paths are eliminated by having a config module that refers to a json on the user server. Follow that pattern, or make paths relative. Of course if the path gets a lot of data, don't push it up to the shared repository, use the .gitignore file to keep it out ( Github limits the amount of data you can put up there anyways) 


### Never merge

Mistakes are inevitable. Creating a repository in such a way that you can't easily get out of your mistakes is not. At some point you will realize you made a big mistake and want to rewind to an earlier point in your history. If you history is a bunch of sequential commits (this happens when you use rebase), then you just need to rewind back up your linear history. If you have been using merge you don't have a bunch of sequential commits in a way that makes sense. Your history looks like a tree. Do the following enough times:

                     |  |                 
                     |  |
                      \/                 
                       |

And eventually you live in a forest. If you want to go backwards, how? Half of backwards was on one branch and half was on another at best. More likely, you now have hundreds of varied branches that all have part of your history. Good luck rewinding. You should have used rebase. Keep the trees in the forest and out of our code.



                                          ░░▒▒░░░░░░▒▒                                    
                              ░░░░▒▒░░░░░░░░░░░░░░░░▒▒░░                                  
                            ░░░░░░░░░░▒▒▒▒▒▒░░░░░░░░░░▒▒░░                                
                          ▒▒░░░░░░░░░░▒▒▒▒▒▒░░░░░░░░░░░░▒▒░░░░░░░░░░                      
                          ▒▒░░░░░░░░░░▒▒▒▒▒▒░░░░░░░░▒▒▓▓▒▒░░░░░░░░▒▒░░                    
                        ▒▒░░░░░░░░░░░░▒▒▓▓▒▒▒▒▒▒░░░░▒▒▒▒▒▒░░░░▒▒░░░░▒▒                    
                  ░░▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░▒▒░░░░░░▒▒▒▒░░░░▒▒░░░░░░░░▒▒░░▒▒                    
                ▒▒▒▒░░░░░░▒▒▒▒▒▒▒▒▒▒▒▒░░░░░░░░░░░░░░░░░░▒▒▒▒░░▒▒▒▒░░░░▒▒░░                
              ░░▒▒▒▒░░░░░░▒▒▒▒▒▒▒▒▒▒░░░░▒▒░░░░░░░░░░░░░░░░▒▒▒▒░░░░░░░░░░▒▒                
          ░░▒▒▒▒░░░░░░░░░░░░▒▒▒▒▒▒▒▒▒▒░░░░░░░░▒▒░░░░░░░░▒▒▒▒▒▒░░▒▒░░▒▒▒▒▒▒▒▒              
          ░░░░░░▒▒░░░░░░░░▒▒▒▒▒▒▒▒░░▒▒▒▒▒▒▒▒▓▓▓▓▒▒▒▒░░▒▒▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒              
    ░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░▒▒▒▒▓▓▒▒░░░░▒▒▒▒▒▒▒▒▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒            
    ░░░░░░░░░░▒▒▒▒▓▓▒▒▒▒▒▒▒▒▒▒▒▒▓▓░░░░▒▒▒▒▒▒▒▒██░░▒▒░░▒▒▓▓▒▒▒▒▒▒▒▒▒▒▒▒░░▒▒▒▒▒▒▒▒▒▒          
    ░░▒▒░░░░░░▒▒▒▒▒▒▒▒▒▒▓▓░░▓▓▒▒▓▓▓▓▒▒░░▒▒▓▓▓▓▒▒░░▒▒░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▓▒▒▒▒░░▒▒▒▒▒▒░░        
    ░░░░░░░░░░░░▓▓▒▒▒▒▒▒░░▒▒▓▓▓▓▒▒▓▓██▓▓████▓▓▓▓▒▒▓▓▓▓▒▒▓▓▒▒▓▓▓▓▒▒▒▒▓▓▓▓▒▒▒▒▒▒▒▒▒▒░░▒▒░░    
    ░░▒▒░░░░░░▒▒▒▒▓▓▒▒▓▓░░░░▒▒▒▒██▓▓▓▓██████▒▒██▓▓▓▓▓▓▒▒▓▓▓▓▓▓▓▓▓▓▒▒▓▓▓▓▒▒░░░░▒▒░░░░░░▒▒▒
      ▒▒▒▒▒▒▒▒▒▒▓▓▒▒▓▓▒▒▒▒▒▒▓▓██▒▒██████▓▓▓▓▓▓▓▓▓▓▒▒▓▓▓▓▓▓▓▓▓▓▒▒▒▒▓▓▒▒▒▒▒▒▒▒░░░░░░░░░░░░  
        ▒▒▒▒▒▒▒▒▓▓▓▓▓▓▓▓▓▓▓▓▓▓██▓▓████▓▓░░░░▓▓  ▓▓▓▓▓▓▓▓▓▓▒▒▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒░░░░░░░░▒▒░░
          ▒▒▒▒▒▒▒▒▓▓▓▓▓▓▒▒▓▓██░░▒▒▓▓      ▓▓▓▓  ▓▓▓▓▓▓▓▓▒▒░░░░▓▓▓▓▒▒▓▓▓▓▒▒▒▒▒▒░░░░▒▒▒▒  
          ░░░░    ▓▓▒▒  ▒▒▓▓▓▓    ▒▒▒▒▒▒▓▓▒▒▓▓░░▒▒▓▓░░      ▓▓▓▓▒▒░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░  
                          ▓▓▓▓      ▓▓▒▒▓▓▓▓▓▓▒▒▓▓▓▓      ░░▓▓      ░░▒▒░░▒▒░░░░░░    
                          ▒▒▒▒▓▓▓▓▒▒██▒▒▓▓▓▓▒▒▓▓▓▓    ▓▓▒▒▓▓                              
                              ▓▓▓▓▒▒▒▒▓▓▒▒▓▓▓▓▓▓▓▓▒▒▓▓▓▓░░                                
                                ▓▓▓▓▒▒▓▓▒▒▒▒██████▓▓                                      
                                  ▒▒▓▓▓▓▓▓▓▓▓▓▒▒░░                                        
                                ▒▒▒▒▓▓▒▒▓▓▓▓▓▓                                            
                                ▒▒▒▒▓▓▒▒▓▓▓▓                                              
                                ▒▒▒▒▓▓▒▒▓▓▓▓                                              
                                ▒▒▒▒▒▒▓▓▓▓                                                
                                ▒▒▓▓▒▒▓▓▓▓                                                
                              ▓▓▒▒▒▒▒▒▓▓▓▓                                                
                              ▓▓▒▒▒▒▒▒▓▓▓▓▒▒                                              
                            ▒▒▒▒▓▓▒▒▒▒▓▓▓▓▒▒                                              
                          ▒▒▓▓▒▒▓▓▓▓▓▓▓▓▓▓▒▒░░  ░░                                        
                ░░▒▒▒▒▒▒▒▒▒▒▒▒▓▓▒▒▒▒▓▓▓▓▒▒██▓▓░░▒▒  ░░░░                                  
        ░░▒▒▓▓▒▒▒▒▒▒▓▓▒▒▒▒▓▓▒▒▓▓▒▒▓▓▒▒▒▒▓▓▒▒▓▓▒▒▒▒▒▒▒▒▒▒░░                                
    ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▓▒▒▒▒▒▒▓▓▒▒▓▓▓▓▒▒▒▒▓▓▒▒▓▓▒▒▒▒▓▓▒▒▒▒▒▒▓▓▓▓▒▒▒▒                        
                                           

