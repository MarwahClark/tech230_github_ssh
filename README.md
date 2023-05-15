# tech230_github_ssh
### How to....

- In the gitbash terminal go back to the home directory using `pwd`
- once arrived in your home directory run the code `ls -a` to find the directory `.ssh/` this is where all your keys should be stored.
- if you cant find the key run the code `cd .ssh` and if its still not found, make a file called .ssh using `mkdir .ssh`
- to generate a key run the code `ssh-keygen -t rsa -b 4096 -C "youremail@wherever.com"` 
- once the key has been generated it will give you the option to name your file
- it will then ask if you want to add a password.
- after this you will see your key pair as it would have made a key pair (public and private key)
- to double check the key has been made run the code `ls` in your folder. you should see another key with the exact same name but a `.pub` extension. this is the public key
- next enter your github account and press on settings.
- once in settings, go to the `SSH and GPG keys` section.this is where you will be able to manage your keys
- select the `new SSH` button. add a title (preferably the same name as your keys on gitbash)
- keep the key type as authentication.
- in order to take the contents from your public key in your local machine into the key section, you enter gitbash and run the code `cat yourkeyname.pub` 
- it will then show you all the contents to the key. copy this with no white space and enter into the key section in github. it will ask you to enter your password on github
- to test out if yourkey has worked run the code `ssh -T git@github.com` you should then see a permission denied message.
- after this run the code ` ssh-agent -s` to assign an agent and then `ssh-add ~/.ssh/yoursshfilename`
- to check that it has connected run the code `ssh -T git@github.com`
- next enter your folder that has your current git repositories.
- do a `git status` and then a `git add .` finally a `git commit -m (with a comment )` this allows you to make your snapshot local.
- to push it to git hub use the code `git push -u origin main`

### to clone 
- enter github and creat a new repository 
- add a readme file
- usse an `ssh` code and copy the url
- going back to gitbash, go back to the overall folder using `cd ..` (which takes you back 1) and run the code `git clone (paste your url)`
- to double check its worked run the code `ls`