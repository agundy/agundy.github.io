---
layout: post
title: Running Tests in Vagrant From Vim
tags:
- Programming
- Rspec
- Ruby
- Vim
---

I have been using Vim to develop for Ruby on Rails for almost a year now and I just recently set myself up so that I could run my tests from Vim, using https://github.com/thoughtbot/vim-rspec. At BookBub we currently run our development applications inside of Vagrant so this only changed the setup a little bit. To get it to work in my Iterm on Macos with Vagrant I installed the `thoughtbot/vim-rspec` plugin and then added the following lines to my configuration: 

```
" RSpec.vim mappings
let g:rspec_command = "!vagrant ssh -c \"rspec --no-color {spec}\""
let g:rspec_runner = "os_x_iterm"
map <Leader>t :call RunCurrentSpecFile()<CR>
map <Leader>s :call RunNearestSpec()<CR>
map <Leader>l :call RunLastSpec()<CR>
map <Leader>a :call RunAllSpecs()<CR>
```

Let me know if this helped you or have any questions!
