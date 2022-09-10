# Best practices 


        _..._      .-'''-.                                   
    .-'_..._''.  '   _    \_______                          
  .' .'      './   /` '.   \  ___ `'.        __.....__      
 / .'         .   |     \  '' |--.\  \   .-''         '.    
. '           |   '      |  | |    \  ' /     .-''"'-.  `.  
| |           \    \     / /| |     |  /     /________\   \ 
| |            `.   ` ..' / | |     |  |                  | 
. '               '-...-'`  | |     ' .\    .-------------' 
 \ '.          .            | |___.' /' \    '-.____...---. 
  '. `._____.-'/           /_______.'/   `.             .'  
    `-.______ /            \_______|/      `''-...... -'      
           
                                                ,---,  
                                               ,`--.' |  
                        ,--,    ,--,           |   :  :  
                      ,--.'|  ,--.'|           '   '  ;  
         .---.        |  | :  |  | :           |   |  |  
        /. ./|        :  : '  :  : '           '   :  ;  
     .-'-. ' |  ,---. |  ' |  |  ' |           |   |  '  
    /___/ \: | /     \'  | |  '  | |           '   :  |  
 .-'.. '   ' ./    /  |  | :  |  | :           ;   |  ;  
/___/ \:     .    ' / '  : |__'  : |__         `---'. |  
.   \  ' .\  '   ;   /|  | '.'|  | '.'|         `--..`;  
 \   \   ' \ '   |  / ;  :    ;  :    ;        .--,_     
  \   \  |--"|   :    |  ,   /|  ,   /         |    |`.  
   \   \ |    \   \  / ---`-'  ---`-'          `-- -`, ; 
    '---"      `----'                            '---`" 



### Pep-8 check 

Pep-8 (https://peps.python.org/pep-0008/) is the way to make sure your code is in line with standards. You can get any one of a variety of tools to help you fix formatting mistakes. In any package I build since 2022 you can run a lint easily, and the CI will have a lint checker. What is impossible to automate is using the proper convention in terms of how classes versus functions are called. Classes have caps, functions do not. If you want what you write to make sense to everyone keep your code in line with conventions. In extreme cases your code will do something different than you programmed it to just because the formatting is incorrect.


### When in doubt, comment

If there is any part of your work that would not be obvious, explain it in the comments. If in doubt about whether it is obvious, just add comments. We can take them out easily, but if we don't know what you intended, we can't put them in for you.


### Name your folders and files without spaces

Eventually, you will want to do something in command line with some other method that only deals well with things with sensible names. I know your folder entitled 'I don't care about my data' has a perfectly sensible name in your eyes, but for command line that is at a minumum 6 different variables, assuming you know how to write a special charecter to get the "'" in there. If you want such a long name it should be 'I_do_not_care_about_my_data' . The same goes for file names and all variables. Keep all names and variables space free. 


### Stay off the main branch, open your own

There is one main branch, and the bigger a project gets, the more you should stay off it, always. The proper way to change things is open your own fork (or branch if you are an invited to), change things there, then put in a pull request. This is much better for other people who have expectations that the main branch is fairly stable, and won't have an accidental bug popping up every other commit. In theory you could play on the main branch, and never push it back. In reality things never work that way for long. It's customary to open a branch with your github username and then '/exploring' to play around. If you then want to catch your branch up to changes on the main, rebase it.

### Never merge

Mistakes are inevitable. Creating a repository in such a way that you can't easily get out of your mistakes is not. At some point you will realize you made a big mistake and want to rewind to an earlier point in your history. If you history is a bunch of sequential commits (this happens when you use rebase), then you just need to rewind back up your linear history. If you have been using merge you don't have a bunch of sequential commits in a way that makes sense. Your history looks like a tree. Do the following enough times:

                     |  |                 
                     |  |
                      \/                 
                       |

And eventually you live in a forest. If you want to go backwards, how? Half of backwards was on one branch and half was on another at best. More likely, you now have hundreds of vaired branches that all have part of your history. Good luck rewinding. You should have used rebase. Keep the trees in the forest and out of our code.
                                                                                              
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
  ░░▒▒░░░░░░▒▒▒▒▓▓▒▒▓▓░░░░▒▒▒▒██▓▓▓▓██████▒▒██▓▓▓▓▓▓▒▒▓▓▓▓▓▓▓▓▓▓▒▒▓▓▓▓▒▒░░░░▒▒░░░░░░▒▒▒▒  
      ▒▒▒▒▒▒▒▒▒▒▓▓▒▒▓▓▒▒▒▒▒▒▓▓██▒▒██████▓▓▓▓▓▓▓▓▓▓▒▒▓▓▓▓▓▓▓▓▓▓▒▒▒▒▓▓▒▒▒▒▒▒▒▒░░░░░░░░░░░░  
        ▒▒▒▒▒▒▒▒▓▓▓▓▓▓▓▓▓▓▓▓▓▓██▓▓████▓▓░░░░▓▓  ▓▓▓▓▓▓▓▓▓▓▒▒▓▓▓▓▓▓▓▓▒▒▒▒▒▒▒▒░░░░░░░░▒▒░░▒▒
          ▒▒▒▒▒▒▒▒▓▓▓▓▓▓▒▒▓▓██░░▒▒▓▓      ▓▓▓▓  ▓▓▓▓▓▓▓▓▒▒░░░░▓▓▓▓▒▒▓▓▓▓▒▒▒▒▒▒░░░░▒▒▒▒▒▒  
          ░░░░    ▓▓▒▒  ▒▒▓▓▓▓    ▒▒▒▒▒▒▓▓▒▒▓▓░░▒▒▓▓░░      ▓▓▓▓▒▒░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒░░  
                          ▓▓▓▓      ▓▓▒▒▓▓▓▓▓▓▒▒▓▓▓▓      ░░▓▓          ░░▒▒░░▒▒░░░░░░    
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
  ░░▒▒▒▒▒▒▒▒▒▒▒▒▓▓▒▒▒▒▒▒▒▒▒▒▒▒▓▓▓▓▒▒▒▒▒▒▒▒▓▓▒▒▓▓▒▒▒▒▒▒▒▒▒▒▒▒▓▓▓▓▒▒░░                      
  ░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▓▒▒▒▒░░░░░░▒▒▒▒▒▒                      
  ░░▒▒▒▒▒▒▒▒▒▒░░▒▒░░▒▒▒▒▓▓▓▓▒▒▒▒░░░░░░▒▒▒▒▒▒░░▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▓░░░░                      
    ▒▒▒▒▓▓▒▒▒▒▒▒▒▒▒▒▓▓▓▓▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▓▓▒▒  ▓▓  ░░░░░░                              
            ░░▒▒▒▒▒▒░░    ▓▓▓▓░░▓▓▒▒▒▒▒▒▒▒                                                

