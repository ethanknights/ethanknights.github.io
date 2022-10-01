
If installations already ran, skip to __Serve__.

# First-Time Setup instructions (Mac)


We assume that ruby/gem/jekyll are not setup on a fresh mac.
Setup the user's (usr) ruby: 
```sh

brew install chruby ruby-install
ruby-install ruby
```

Add this to startup shell (vscode ~./zshrc):
```sh
add to startup:
#Ruby (homebrew install)
#-------
#source /opt/homebrew/opt/chruby/share/chruby/auto.sh
export PATH="/Users/ethan.knights/.rubies/ruby-3.1.2/bin:$PATH"
```


Verify:
```sh
which ruby
```

Clone repo:
```sh
mkdir tmp
cd tmp
git clone https://github.com/ethanknights/ethanknights.github.io
```

One-time setup:
```sh
gem install jekyll bundler
jekyll new ethanknights.github.io --force
#remove newly intitated duplicate files:
rm -f ethanknights.github.io/index.markdown
```


If first-time installation, remember that gem3.0 does not come with webrick (https://stackoverflow.com/questions/69890412/bundler-failed-to-load-command-jekyll + https://github.com/github/pages-gem/issues/752) so use:
```sh
bundle add webrick
```
<br>

# Serve
From repo directory, create local server:
```sh 
bundle exec jekyll serve

#cmd+T
open -a Firefox http://127.0.0.1:4000/

#Troubleshooting:
#Remember to verify server address (e.g. http://localhost:8080/home).
```

