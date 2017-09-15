---
layout: page
title: Personal cheatsheet tl;dr;search
permalink: /cheatsheet/
---


About this page:

This one page cheatsheet is a (more) convenient way to store potential blog posts, interesting resources and technical experiences with the world. Before starting this I used different other platforms like [de.icio.us](https://del.icio.us/alin.mechenici), [twitter](https://twitter.com/alinmechenici), etc.

I encourange you to use the table of contents and Ctrl + f to find more easily.

# Table of Contents

My Linux Cheatsheet
- [My Linux Checklist](#my-linux-checklist)
- [Applications installed](#applications-installed)
-- [Install apps](#install-apps)
- [Applications](#applications)
-- [Zeal](#zeal)
-- [F.lux](#f.lux)
-- [Neo4j](#neo4j)
-- [VYM](#vym)
-- [Planner](#planner)
-- [Libreoffice](#libreoffice)
-- [Gnome-Commander](#gnome-commander)
-- [Dia](#dia)
-- [Mpv](#mpv)
-- [Chromium](#chromium)
-- [Firefox](#firefox)
-- [Docker](#docker)
-- [KeePass](#keepass)
-- [OpenSSL](#openssl)
-- [OpenSSH](#openssh)

My dotfiles
- [Window Managers](#window-managers)
-- [AwesomeWM](#awesomewm)
-- [i3WM](#i3wm)
-- [Emacs](#emacs)
-- [Mutt](#mutt)
-- [Zsh](#Zsh)
-- [bin scripts](#bin-scripts)

My iOS Cheatsheet (*soon)

- [iOS Applications](#ios-applications)
- [iOS Workflows](#ios-workflows)

Programs (external) Cheatsheet

- [Platforms](#platforms)
- [Programming Languages](#programming-languages)
- [Front-End Development](#front-end-development)
- [Back-End Development](#back-end-development)
- [Computer Science](#computer-science)
- [Big Data](#big-data)
- [Theory](#theory)
- [Books](#books)
- [Editors](#editors)
- [Tools](#tools)
- [Development Environment](#development-environment)
- [Entertainment](#entertainment)
- [Databases](#databases)
- [Media](#media)
- [Security](#security)
- [Content Management System](#content-management-system)
- [Project Management](#project-management)
- [Miscellaneous](#miscellaneous)

Keyboard Shortcuts

- [Keyboard description](#keyboard-description)
- [Keyboard shortcuts automation](#keyboard-shortcuts-automation)

WebApps Shortcuts

- [Gmail](#gmail)
- [RemembertheMilk](#rememberthemilk)

Apps Shortcuts

- [Emacs shortcuts](#emacs-shortcuts)
- [Mutt shortcuts](#mutt-shortcuts)
- [VYM shortcuts](#vym-shortcuts)
- [Firefox shortcuts](#firefox-shortcuts)
- [Remember the Milk shortcuts](#remember-the-milk-shortcuts)

===============================================================

# My Linux Cheatsheet

## Window Managers

### AwesomeWM

    startx

	install: apt-get install awesome

	chose_theme = "default-modified"

	~/.config/awesome/rc.lua

    awesome -k

& su apt install xev
& su apt install lxappearance
& su apt install i3lock


Notes:

* xev = keyboard pointer (x-event)


- [FontAwesome](https://github.com/FortAwesome/Font-Awesome/releases)

- [playerctl](https://github.com/acrisci/playerctl/releases)

- [mulimedia keys](https://faq.i3wm.org/question/3747/enabling-multimedia-keys/?answer=3759#post-id-3759)

- [Arc Firefox Theme](https://github.com/horst3180/arc-firefox-theme) & [Mozilla Addons](https://addons.mozilla.org/en-US/firefox/collections/horst3180/a/)

- [Arc Theme debian](https://software.opensuse.org/download.html?project=home%3AHorst3180&package=arc-theme)

- [f.lux](https://justgetflux.com/linux.html)

### i3WM

    apt install i3

Favorite font

    font pango:System San Francisco Display 10

Start compton

    exec compton

Always open thunar window manager when i3 starts

    exec_always thunar # open window manager

Stop the terminal bell (can be placed in a script or in i3 config file)

    xset b off

Make apps start from terminal / S-r

     wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
     sudo tar -xzf postman.tar.gz -C /opt
     rm postman.tar.gz
     sudo ln -s /opt/Postman/Postman /usr/bin/postman

Key bindings

Print key = printscreen

    bindsym Print exec bash /home/alin/bin/alinscreencapture

S+Print = printscreen, open in a photo manipulation program, save.

    bindsym Shift+Print exec bash /home/alin/bin/alinscreencaptureandedit

Open a design app

    bindsym $mod+Shift+d exec bash /home/alin/bin/designer

Open telegram

    bindsym $mod+Shift+t exec bash /home/alin/bin/telegram

===============================================


#### search

    apt-cache search

#### SSH

    sysv-rc-conf

    /etc/init.d/ssh start

    /etc/init.d/sshd_config start/stop

### Mounded

    lsbsk - what is mounted

    dmesg -c = clear

## Mutt

Mutt settings for icloud email ([*](https://forums.freebsd.org/threads/44264/))

    set imap_user = "user"
    set from = "user@icloud.com"
    set smtp_url = "smtp://user@smtp.mail.me.com:587/"

    set folder = "imaps://user@imap.mail.me.com/"
    set spoolfile = "imaps://user@imap.mail.me.com/INBOX"
    set postponed = "+Drafts"
    set record = "+Sent Messages"

    set imap_pipeline_depth=0

    set header_cache = "~/.mutt/cache/headers"
    set message_cachedir = "~/.mutt/cache/bodies"
    set certificate_file = "~/.mutt/certificates"

## [F.lux](https://github.com/xflux-gui/xflux-gui)

##### Install dependencies

  sudo apt-get install git python-appindicator python-xdg python-pexpect python-gconf python-gtk2 python-glade2 libxxf86vm1

##### Download xflux-gui

  cd /tmp

  git clone "https://github.com/xflux-gui/xflux-gui.git"

  cd xflux-gui

   python download-xflux.py

###### EITHER install globally

  sudo python setup.py install

###### EXCLUSIVE OR, install in your home directory. The binary installs
###### into ~/.local/bin, so be sure to add that to your PATH if installing locally.

  python setup.py install --user

###### Run flux

  fluxgui



## Neo4j

The Debian package is available from http://debian.neo4j.org. To use the repository follow these steps:

    wget -O - https://debian.neo4j.org/neotechnology.gpg.key | sudo apt-key add -
    echo 'deb http://debian.neo4j.org/repo stable/' | sudo tee -a /etc/apt/sources.list.d/neo4j.list
    sudo apt-get update

To install Neo4j Community Edition:


   sudo apt-get install neo4j=3.2.3
   apt-get install neo4j=3.2.4


Start:

	service neo4j start

Make defaul homepage in chromium:

     http://localhost:7474/browser/


## OrgMode

Add tasks in OrgMode

* A-Return = *

** A- -> = sub-bullets

* A-arows up/down = Move

* TODO S- -> = To Do

* DONE S- <- = Done

### Checkbox [1/2]

    "["/"]" C-c, C-c adds number of items in checklist

  "["%"]" C-c, C-c adds procentage

- [ ] checkbox

- [X] checkbox checked (C-c, C-c)

- [ ] checkbox 3

### Deadlines

C-c C-d = Add deadlines

* go home

DEADLINE: <2017-07-16 Sun>

### Tags

C-c C-c = Add tags

### Hides

    Cursor tab = hide

    S-tab = hide more

### Save

    C-x C-s = save

### Agenda view

Start agenda view C-c [

A-x org-agenda

C-0 = back to original file

q = exit screen

* case sensitive ("m" for all or "M" for TODO)



C-h t = tutorial


=============================================

# MPV

    - ls music

    - find

> stream > playlist (1)

    cat playlist 1

    find -type f (files) | grep -v pl[0-9]>playlist1

    mpv --playlist pl1


=============================================

# Emacs

Useful terminal commands for working with emacs:

    emacs -nw = new emacs window

    watch tree = watch tree in terminal for 3 min

## Tricks

C-x C-q (cont..)

C-x C-s =  edit files and folders as a file

A-/ auto-complete cycle


## emacs checklist:

- medium, jekyll
- erc
- mutt
- slack
- excel
- notes / remember
- calendar gcal.el
- codepad
- ipython
- python compiler
- neotree
- google maps
- google translate
- google here *search
- eshell
- hackernews
- battery (laptop)
- dashboard
- bookmarks
- trump (webdav, ssh, )
- dropbox
- email
- telegram
- firefox-mode
- playerctl
- alin_modes
- emacs wm
- templates
- web server (w/ broweser sync)
- sync content with mobile and ipad via calendar and dropbox/mega/box
- excel updates
- artist mode
- org-mind-map
- github
- emmet mode (always on)

..............................................

.............................................

## Compilation example

    emacs compile python ~/py/working/src/app.py

    M-x compile (enter)

	python ~/py/working/src/app.py

.............................................

# Emacs config and other daemons

## Theme and settings

    ; setup theme
    (load-theme 'misterioso) ; 'tango-dark


    ; remove menu, tab and scroll
    (menu-bar-mode -1)
    (tool-bar-mode -1)
    (scroll-bar-mode 0)

    ;text increasing
    (text-scale-adjust 1)


    ; start emacs in fullscreen mode
    (add-hook 'emacs-startup-hook 'toggle-frame-maximized)


    ; open browser where the cursor is
    (defun webbrowser-visit-thing-at-point()
        (interactive)
    (start-process "emacs-webbrowser-visit-thing-at-point-process" "*Messages*" "/home/rider/.emacs.d/x/webbrowserwrapper" (thing-at-point 'url)))
    (global-set-key [f2] 'webbrowser-visit-thing-at-point)

    ; use left, right arrows to visit another frame
    (global-set-key (kbd "C-c <left>") 'previous-multiframe-window)
    (global-set-key (kbd "C-c <right>") 'next-multiframe-window)


### codepad.org integration

    (add-to-list 'load-path ".emacs.d/roaming/codepad.el") ;; replace PATH with the path to codepad.el
    (autoload 'codepad-paste-region "codepad" "Paste region to codepad.org." t)
    (autoload 'codepad-paste-buffer "codepad" "Paste buffer to codepad.org." t)
    (autoload 'codepad-fetch-code "codepad" "Fetch code from codepad.org." t)



## Run a workflow in multi-windows

// Mx- RET notes



   (defun notes()
   	   (interactive)
	   ;(find-file "book.md")
	   (find-file "/home/alin/.emacs.d/notes")
	   (split-window-right)
	   (find-file "/home/alin/Work/TODO.md")

	   ;(find-file "/home/alin/.config/awesome/rc.lua")
	   ;  (split-window-right)
	   ;  (split-filet "/home/alin/work/README.md")
	   ;(split-window-right)
	   ;(find-file "/home/alin/.emacs.d/init.el")
	   ;(split-window-right)


	   ;(find-file "/home/alin/work/start.m")
	   (balance-windows))


Call "notes": f2


     (defun file-notes()
     	    (interactive)
  	    (find-file (concat (getenv "HOME") "/.emacs.d/notes")))
	    (global-set-key [f3] 'file-notes)
	    (global-set-key (kbd "<XF86Search>") 'file-notes)
	    (global-set-key (kbd "<XF86AudioRaiseVolume>") 'file-notes)



// M-x RET alin_start


    (defun alin_start()
        (interactive)

    ;(find-file "book.md")
    (find-file "/home/user/.emacs.d/init.el")
    (split-window-right)
    (find-file "/home/alin/work/planning/TODO.md")
    ;  (split-window-right)
    ;  (split-filet "/home/alin/work/README.md")
    (split-window-right)
    (find-file "/home/alin/work/now.py")
    (split-window-right)
    (find-file "/home/alin/work/start.md")
    (balance-windows))
    ;(add-hook 'emacs-startup-hook 'alin_start)

    ;(add-hook 'text-mode-hook 'auto-fill-mode)

* change files path with your own

## Dash-at-point (Zeal integration)

    ;(global-set-key "bla" 'zeal-at-point)
    (global-set-key [f1] 'zeal-at-point)
    (global-linum-mode t)

    ;; Use multiple docsets
    ;(add-to-list 'zeal-at-point-mode-alist '(python-mode . ("python" "django")))


## Neotree


    (add-to-list 'load-path "~/.emacs.d/neotree")
        (require 'neotree)
    (global-set-key [f8] 'neotree-toggle)

    (setq misterioso (if (display-graphic-p) 'icons 'arrow)) ; neo-theme


--------------------------------------------

# Programming Cheatsheet

## Platforms

- [Android-Cheatsheet-For-Graphic-Designers](http://petrnohejl.github.io/Android-Cheatsheet-For-Graphic-Designers/)
- [Arduino_Cheat_Sheet.pdf](https://static.sparkfun.com/learn/materials/8/Arduino_Cheat_Sheet.pdf)
- [docker](https://github.com/wsargent/docker-cheat-sheet)
    - [dockerfiles](https://github.com/jessfraz/dockerfiles)
- [ios-cheat-sheet](https://github.com/Avocarrot/ios-cheatsheet)
    - [iOS-App-Performance-Cheatsheet](https://github.com/danielamitay/iOS-App-Performance-Cheatsheet)
    - [UI-Testing-Cheat-Sheet](https://github.com/joemasilotti/UI-Testing-Cheat-Sheet)
- [saltstack](https://github.com/saltstack/salt/wiki/Cheat-Sheet)
- [nginx-cheatsheet](https://github.com/SimulatedGREG/nginx-cheatsheet)


## Programming Languages

- [Ada-cheat-sheet](http://www.digilife.be/quickreferences/QRC/Ada%20Reference%20Card.pdf)
- [assembly-cheat-sheet](http://www.jegerlehner.ch/intel/)
- [coffeescript_cheatsheet](https://github.com/icebob/coffeescript_cheatsheet/)
- [c-ansi-cheat-sheet](http://www.digilife.be/quickreferences/qrc/c%20reference%20card%20(ansi)%202.2.pdf)
- [c#-cheat-sheet ](http://www.digilife.be/quickreferences/QRC/Core%20CSharp%20and%20.NET%20Quick%20Reference.pdf)
- [cpp-cheat-sheet](https://isocpp.org/blog/2012/12/c11-a-cheat-sheet-alex-sinyakov)
- [clojure-cheat-sheet](https://clojure.org/cheatsheet)
- [clojurescript-cheat-sheet](http://cljs.info/cheatsheet/)
- [dart-cheat-sheet](http://dartlangfr.net/dart-cheat-sheet/)
- [delphi-cheat-sheet](http://www.cheat-sheets.org/saved-copy/dquick.pdf)
- [dotnet-cheat-sheet](https://dzone.com/refcardz/coredotnet)
- [elixir-cheat-sheet](https://media.pragprog.com/titles/elixir/ElixirCheat.pdf)
- [elm-cheat-sheet](https://github.com/izdi/elm-cheat-sheet)
- [erlang-cheat-sheet](http://www.cheat-sheets.org/saved-copy/Erlang.CheatSheet(1.0).pdf)
- [emoji-cheat-sheet](https://github.com/WebpageFX/emoji-cheat-sheet.com)
- [f#-cheat-sheet](http://dungpa.github.io/fsharp-cheatsheet)
- [golang-cheat-sheet](https://github.com/a8m/go-lang-cheat-sheet)
    - [Cheat sheet for some of the common concurrent flows in Go](https://github.com/rakyll/coop)
- [java-cheat-sheet](http://introcs.cs.princeton.edu/java/11cheatsheet/)
    - [java8-cheat-sheet](https://github.com/BafS/Java8-CheatSheet)
- [javascript-cheat-sheet](http://www.cheatography.com/davechild/cheat-sheets/javascript/)
    - [es6-cheatsheet](https://github.com/DrkSephy/es6-cheatsheet)
    - [javascript-design-pattern](https://github.com/nnupoor/js_designpatterns)
    - [npm-vs-yarn-cheat-sheet](https://shift.infinite.red/npm-vs-yarn-cheat-sheet-8755b092e5cc#.91l58dovs)
    - [npm-vs-yarn-cheat-sheet](https://github.com/areai51/yarn-cheatsheet)
- [lisp-cheat-sheet](http://faculty.smcm.edu/acjamieson/s13/LispCheatSheet.pdf)
- [lua-cheat-sheet](http://lua-users.org/files/wiki_insecure/users/thomasl/luarefv51single.pdf)
- [objective-c-cheat-sheet](https://github.com/iwasrobbed/Objective-C-CheatSheet)
- [ocaml-cheat-sheet](http://ocaml.org/docs/cheat_sheets.html)
- [python-cheat-sheet](http://www.cheatography.com/davechild/cheat-sheets/python/)
    - [Python Cheat Sheet](https://perso.limsi.fr/pointal/_media/python:cours:mementopython3-english.pdf)
    - [Python Cheat Sheet](https://docs.google.com/file/d/0B9VT_L2CDnKvODYyNTc5NjktYmMyOC00NDFkLTliNTctMzQzMTAzYjUyYmYy/view?pli=1)
    - [Python Crash Course - Cheat Sheets](http://ehmatthes.github.io/pcc/cheatsheets/README.html)
    - [python feature](https://github.com/PythonCharmers/python-future)
    - [Python Basics For Data Science Cheat Sheet](https://www.datacamp.com/community/tutorials/python-data-science-cheat-sheet-basics)
- [php-cheat-sheet](http://www.cheatography.com/davechild/cheat-sheets/php/)
    - [PHP7-Reference](https://github.com/tpunt/PHP7-Reference)
- [perlcheat](http://perldoc.perl.org/perlcheat.html)
- [r-cheat-sheet](http://cran.r-project.org/doc/contrib/Baggott-refcard-v2.pdf)
    - [R Cheat Sheets](https://www.rstudio.com/resources/cheatsheets/)
- [racket-cheat-sheet](http://docs.racket-lang.org/guide/)
- [ragel-cheat-sheet](https://github.com/calio/ragel-cheat-sheet)
- [rebol-cheat-sheet](http://rebol.desajn.net/cheatsheet.html)
- [ruby-cheat-sheet](https://github.com/brennovich/cheat-ruby-sheets)
    - [A collection of Ruby Net::HTTP examples](https://github.com/augustl/net-http-cheat-sheet)
- [rust-cheat-sheet](https://static.rust-lang.org/doc/0.9/complement-cheatsheet.html)
- [scala-cheat-sheet](http://docs.scala-lang.org/cheatsheets/)
- [scheme-cheat-sheet](http://courses.cs.washington.edu/courses/cse341/02wi/scheme/cheat-sheet.html)
- [shell-cheat-sheet](https://github.com/NisreenFarhoud/Bash-Cheatsheet)
    - [bash cheat sheet](https://learncodethehardway.org/unix/)
        - [awesome-bash](https://github.com/awesome-lists/awesome-bash)
        - [bash redirections](https://github.com/pkrumins/bash-redirections-cheat-sheet)
    - [fish](https://fishshell.com/docs/current/commands.html)
    - [awesome-shell](https://github.com/alebcay/awesome-shell)
    - [oh-my-zsh cheatsheet](https://github.com/robbyrussell/oh-my-zsh/wiki/Cheatsheet)
- [smalltalk-cheat-sheet](http://stephane.ducasse.free.fr/Teaching/0809Turino/st-cheatsheet.pdf)
- [swift cheatsheet](https://github.com/iwasrobbed/Swift-CheatSheet)
    - [Playgrounds](https://github.com/uraimo/Awesome-Swift-Playgrounds)
    - [swift design patterns](https://github.com/ochococo/Design-Patterns-In-Swift)
- [tcl-cheat-sheet](http://wiki.tcl.tk/10710)
- [typescript-cheat-sheet](http://www.typescriptlang.org/Handbook/)

## Front-End Development

- [angular2](https://angular.io/cheatsheet)
- [angularjs](http://www.cheatography.com/proloser/cheat-sheets/angularjs/)
- [SCSS cheatsheet](https://sass-cheatsheet.brunoscopelliti.com)
- [CSS Flex Box](https://d13yacurqjgara.cloudfront.net/users/248947/screenshots/1742074/attachments/282954/flexboxsheet.pdf)
- [sass/SCSS functions cheatsheet](https://gist.github.com/AllThingsSmitty/3bcc79da563df756be46)
- [ember-js](http://www.cheatography.com/mwore/cheat-sheets/ember-js/)
- [es6-cheatsheet](https://github.com/DrkSephy/es6-cheatsheet)
- [font-awesome](http://fontawesome.io/cheatsheet/)
- [jquery](https://oscarotero.com/jquery/)
    - [jquery-cheatsheet](http://lab.abhinayrathore.com/jquery-cheatsheet/)
- [react-cheatsheet](https://reactcheatsheet.com/)
- [react-native-cheat-sheet](https://github.com/refinery29/react-native-cheat-sheet)
- [react-native-styling-cheat-sheet](https://github.com/vhpoet/react-native-styling-cheat-sheet)
- [redux](http://ricostacruz.com/cheatsheets/redux.html)
- [underscore-cheat-sheet](http://f.cl.ly/items/093o0l2Y3u130y0W0c0x/underscore-cheat-sheet.pdf)
- [webpack](https://github.com/petehunt/webpack-howto)
- [\<head> Cheat Sheet](http://gethead.info/)
- [page-load Cheat Sheet](https://developers.google.com/speed/docs/insights/about)
- [Bootstrap 4](https://hackerthemes.com/bootstrap-cheatsheet/)
- [jest-cheat-sheet](https://github.com/sapegin/jest-cheat-sheet)
- [flexbox-cheatsheet](http://vudav.github.io/flexbox-cheatsheet/)

## Back-End Development

- [flask](https://docs.google.com/file/d/1pnwfq8v5Ph4Xn8ttv9P_TLnrRbT9-S_v-KdZiEcx64vlGYkC0SoMfZOs0NYN/edit?usp=drive_web)
- [laravel-cheatsheet](https://github.com/jesseobrien/laravel-cheatsheet)
- [ror](http://www.cheatography.com/davechild/cheat-sheets/ruby-on-rails/)
- [web2py](https://dl.dropboxusercontent.com/u/18065445/web2py/web2py_cheatsheet.pdf)
- [nodejs](https://gist.github.com/LeCoupa/985b82968d8285987dc3)
- [django](http://awesome-django.com)
- [django-cheatsheet](https://www.mercurytide.co.uk/media/resources/django-cheat-sheet.pdf)
- [syscall-cheatsheet](http://syscalls.kernelgrok.com/)

## Big Data
- [machine-learning-cheat-sheet](https://github.com/soulmachine/machine-learning-cheat-sheet)

## Databases

- [CouchDB Cheatsheet](https://wiki.apache.org/couchdb/API_Cheatsheet)
- [MongoDb-cheat-sheet](https://github.com/leojavier/MongoDb-cheat-sheet)
- [mysql-cheat-sheet](http://www.cheatography.com/davechild/cheat-sheets/mysql/)
- [Oracle_Programming](https://en.wikibooks.org/wiki/Oracle_Programming/SQL_Cheatsheet)
- [postgresql](https://dzone.com/refcardz/essential-postgresql)
- [sql-join-cheat-sheet](http://coolshell.cn/articles/3463.html)
- [SQL](http://www.sql-tutorial.net/sql-cheat-sheet.pdf)

## Theory

- [acm-cheat-sheet](https://github.com/soulmachine/acm-cheat-sheet)
- [bigo](http://bigocheatsheet.com/)
- [Theoretical Computer Science Cheat Sheet](http://www.tug.org/texshowcase/cheat.pdf)
- [regular-expression-cheat-sheet](https://github.com/niklongstone/regular-expression-cheat-sheet)
- [rest-foundations-restful](https://dzone.com/refcardz/rest-foundations-restful)

## Editors

- [a_vi_vim_graphical_cheat_sheet_tutorial](http://www.viemu.com/a_vi_vim_graphical_cheat_sheet_tutorial.html)
    - [Vim Quick Reference Card](https://michaelgoerz.net/refcards/vimqrc.pdf)
    - [A really easy to read and comprehensive guide on vim.](https://vim.rtorr.com/)
- [GNU Emacs](https://www.gnu.org/software/emacs/refcards/pdf/refcard.pdf)
    - [Paredit Cheatsheet](https://www.emacswiki.org/emacs/PareditCheatsheet)
- IntellJ IDEA
    - [Windows/Linux](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)
    - [Mac OS X](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)
- [MarkDown Cheat Sheet](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)
- [Eclipse](https://github.com/pellaton/eclipse-cheatsheet)
- [Atom](https://github.com/nwinkler/atom-keyboard-shortcuts)
- [NetBeans](https://netbeans.org/project_downloads/usersguide/shortcuts-80.pdf)
- [Sublime Text 3](https://www.shortcutfoo.com/app/dojos/sublime-text-3-win/cheatsheet)
- [PHPStorm - Mac/Win](https://resources.jetbrains.com/storage/products/phpstorm/docs/PhpStorm_ReferenceCard.pdf)

## Tools

- [awk-nawk-and-gawk-cheat-sheet](http://www.catonmat.net/blog/awk-nawk-and-gawk-cheat-sheet/)
- [curl](https://github.com/bagder/curl-cheat-sheet)
- [dtrace and stap](http://myaut.github.io/dtrace-stap-book/dtrace-stap-cheatsheet.pdf)
- [GDAL/OGR command-line tools](https://github.com/dwtkns/gdal-cheat-sheet)
- [Git Cheat Sheet and Git Flow](https://github.com/arslanbilal/git-cheat-sheet)
    - [git_cheat_sheet](http://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf)
    - [git-cheat-sheet](https://github.com/arslanbilal/git-cheat-sheet)
    - [github-cheat-sheet](https://github.com/tiimgreen/github-cheat-sheet)
    - [git-style-guide](https://github.com/agis/git-style-guide)
    - [git-flow-cheatsheet](https://github.com/danielkummer/git-flow-cheatsheet)
- [latexsheet](http://wch.github.io/latexsheet/)
- [mac-command-line-cheatsheet](https://github.com/herrbischoff/awesome-osx-command-line)
- [matlab-cheatsheet](http://web.mit.edu/18.06/www/Spring09/matlab-cheatsheet.pdf)
- [Octave-cheatsheet](http://ais.informatik.uni-freiburg.de/teaching/ss14/robotics/etc/cheatsheet.pdf)
- [rspec](https://gist.github.com/dnagir/663876)
- [RSpec cheatsheet](https://github.com/eliotsykes/rspec-rails-examples)
- [svn](http://www.abbeyworkshop.com/howto/misc/svn01/)
- [sed-stream-editor-cheat-sheet](http://www.catonmat.net/blog/sed-stream-editor-cheat-sheet/)
- [terminal-mac-cheatsheet](https://github.com/0nn0/terminal-mac-cheatsheet)
- [tmux](https://gist.github.com/andreyvit/2921703)
- [Unix Toolbox](http://cb.vu/unixtoolbox.xhtml)
- [sysadmin](https://github.com/kahun/awesome-sysadmin)
- [systemtap-cheat-sheet](https://github.com/calio/systemtap-cheat-sheet)

## Media

- [favicon-cheat-sheet](https://github.com/audreyr/favicon-cheat-sheet)

## Security

- [HTML5 Security Cheatsheet](https://github.com/cure53/H5SC)
- [Penetration Testing Cheatsheets](https://github.com/jshaw87/Cheatsheets)
- [Security Tools Cheatsheets](https://github.com/andrewjkerr/security-cheatsheets)
- [oauthsecurity](https://sakurity.com/oauth)
- [OWASP Cheat Sheets](https://www.owasp.org/images/9/9a/OWASP_Cheatsheets_Book.pdf)

## Project Management

- [Agile Cheatsheet](http://cheatsheetworld.com/programming/agile-development-cheat-sheet/)
- [Scrum Cheatsheet](https://www.axosoft.com/Downloads/Scrum_Diagram.pdf)
- [Lean Cheatsheet](https://www.cheatography.com/davidpol/cheat-sheets/lean-methodology/pdf_bw/)
- [A set of metodologies in one Cheatsheet (waterfall, agile, lean, xp, etc)](https://www.cheatography.com/nataliemoore/cheat-sheets/system-development-methodologies/pdf_bw/)

## Miscellaneous

- [easings.net](https://github.com/ai/easings.net)
- [math-as-code](https://github.com/Jam3/math-as-code)
- [MobileApp-Pentest-Cheatsheet](https://github.com/tanprathan/MobileApp-Pentest-Cheatsheet)
- [Network-related cheatsheets](http://packetlife.net/library/cheat-sheets/)
- [api-cheat-sheet](https://github.com/RestCheatSheet/api-cheat-sheet)
- [cheatsheets-ai](https://github.com/kailashahirwar/cheatsheets-ai)


=============================================


# Keyboard shortcuts

## Emacs shortcuts

### Intro

    C = Ctrl

    M = Meta key (alt/ mac key)

    RET - Return / Enter key

### Emacs Dictionary

C-h t = tutorial

C-h i = info manual

C-h k = (describe keyboard shortcut)

C-h a = Search documentation

C-h w <command> = shows shortcut

C-l = clear screen

C-d = delete-char

C-q or C-v = insert quoted

C-k = kill line

M-d = kill word

M-u = upcase-word

M-l = downcase-word

M-c = capitalize-word

M-\ = delete orizontal space

C-y = yank

M-y = yank-pop

xclip = mouse buffer

..............................................

## Emacs Important keys

F10 = Compilation

F3 = file

F1 = python print script print("{ " + str() + "}")

F2 = open link in browser at cursor

F3 = New

F4 = Open cursor position in Zeal

F5 = Timestamp

F6 = Undefined

F7 = Mail mode

F8 = Open Neotree

F9 = Undefined

F12 = Undefined

PrtScr = prinscreen

C-Page Up = sound +

C-Page Down = sound -

### Emacs Basics

C-x C-f = Open file

C-x C-s = Save a file

C-x C-w = Save as

C-x s = Save all

C-x C-V = revert to file

M-x = revert buffer

C-x K = close window/buffer

C-x C-c = Close a file

M-j = focus

M-j space = re-organize

M-m = maximize

..............................................

### Text editing

C-_ = undo

C-Space = Begin selection

C-g = cancel selection

C-k = cut selection

C-k = cut line

C-y = paste

C-x r s /# = copy selection to numbered clipboard

C-x r i /# = paste from numbered clipboard
Delete = delete

C-d = Fwd delete

M-d = delete word

D-d = fwd delete word

C-w = kill/cut

C-y = yand/paste

M-x = replace-string RET

..............................................

### Cursor management

M-f/ M-b = Word forward / backward

C-a/C-e = Jump to beginning / end of the line

M+{/ M+} = Paragraph forward / backward

C-v/ M-v = Page forward / backward

M-</ M-> = Document forward / backward

M-C-a/ M+C-e = C Function forward / backward

C-arrow up - next paragraph up

C-arrow down - next paragraph down

C-home = move cursor up

C-end = move cursor bottom

..............................................

### Emacs Search

C-s = Incremental search

C-r = Incremental search reverse

M-C-s = regex incremental search

M-C-r = regex incremental search reverse

M+% = Interactive Search and Replace

M+X = goto-line	Goto Line Number

M-C+b (or esc C+B) = Previous Matching Bracket

M-C+f (or esc Ctrl+F) = Next Matching Bracket


..............................................

### Emacs Formating

M-q = Re-flow Paragraph

M-C+\ = Indent Selection

M-u = Uppercase Word

M-l = Lowercase Word

M-c = Capitalize Word

C-x, C-u = Uppercase Selection

C-x, C-l = Lowercase Selection

C-x,C-+/- = text size

..............................................

### Emacs Macros

C-x ( = start macro

C-x ) = end macro

C-x e = execute macro
    e = again

..............................................

### Emacs Undefined

C-' = Comment

C-; = search

..............................................

### Emacs Buffer & window management

C-x 2 = split orizontal

C-x 3 = split vertical

C-x o = other window

C-x 0 = get rid of other window

C-x 1 = get rid of other windows

M-o = window re-arange

C-x,k =	Close

C-x, b = Next Window

C-x, Ctrl+B = Choose Window

C-x, 1 = Maximize

C-x, 2 = Split Horizontal

C-x, 3 = Split Vertical

C-x, o = Switch Focus Between Windows

M+` = Activate Menu Bar

.............................................

### Emacs Navigation and search

M-g M-g = go to line
    (holt alt and press "g" twice)

A-g A-g = go to line

C-s = interactive search

C-r = interactive search backward

M-> = end of buffer

M-> = beginning of buffer

M-x = occur RET find lines

.............................................

### Emacs Move

C-e - end of line

C-a - beginning of line

C- <- - one word left

C- -> - one word right

C-space, move with arrow = move text selected

C-S, select with arrows = select text

C-S 1,2,3,4,5,6,7,8,9 = move application to tag

.............................................

### Emacs Cut-n-paste

C-space

Esc- <- = delete word

C-d = delete character

C-_ = undo

C-k = delete until end of line

C-y - yank from kill-ring

..............................................

## Package mode

### Packages installed

M-x / package-install

M-x .. erc / join debian = irc

M-x .. magit-mode = git


..............................................

## Other emacs shortcuts

* Settings:  ~/.emacs.d/init.el (initial-scratch-message)

* Shift + left or right arrows to select a region

* emacs Alt +W copy region into clipboard

* emacs Ctrl+W cut  region into clipboard

* emacs Ctrl+Y paste from clipboard into emacs terminal

* Shift+Insert  paste from clipboard

* Save buffer to file: C-x C-s

* Search text: C-s

* Search w/ regular expression: C-s-Alt

* Exit emacs: C-x C-c

* Buffer list: C-x C-b

* Buffer switch: C-x b

* Maximize S-M

* Fullscreen S-F

* Search C-x C-s

* Focus S-j

* Open C-x C-f

* Open Emacs C-F5 (*soon)

* Screen mngm S-Shift-Space

* Undo C-Shift +

=============================================

=============================================

## VYM shortcuts (View Your Mind)

### Scope Heading Editor:

- Ctrl+Shift+P: Superscript

- Ctrl+Shift+B: Subscript

- Ctrl+U: Underline

- Ctrl+I: Italic

- Ctrl+B: Bold

- Alt+R: Richtext

- Alt+I: Font hint

- Ctrl+V: Paste

- Ctrl+X: Cut

- Ctrl+C: Copy

- Ctrl+A: Select and copy all

- Ctrl+Y: Redo

- Ctrl+Z: Undo

- Ctrl+P: Print

- Alt+X: Export As(ASCII)

- Ctrl+S: Export

- Ctrl+O: Import

### Scope Main window:

- F: Follow XLink

- L: Use modifier to draw xLinks

- K: Use modifier to color branches

- J: Use modifier to color branches

- Backspace: Previous slide

- Space: Next slide

- Shift+Left: Previous Map

- Shift+Right: Next Map

- Ctrl+H: History Window

- Alt+S: Script editor

- Shift+S: Slide editor

- Q: Task editor

- Ctrl+T: Tree editor

- E: Heading editor

- N: Note editor

- .: Center on selection

- ,: reset Zoom

- R: Rotate rclockwise

- Shift+R: Rotate counterclockwise

- -: Zoom out

- +: Zoom in

- : Color subtree

- : Color branch

- Ctrl+K: Pick color

- : Set Color

- Shift+F: Find duplicate URLs

- /: Find

- Ctrl+F: Find

- : Unselect all

- Ctrl+I: Select next

- Ctrl+O: Select previous

- M: Move to target

- G: Goto target

- Shift+T: Toggle target

- P: Property window

- Shift+I: Add

- T: Add timestamp

- Shift+X: Remove children

- W: Cycle task status

- Shift+W: Toggle task

- Ctrl+B: Get data from SUSE Bugzilla for subtree

- Shift+B: Get data from SUSE Bugzilla

- B: Create URL to SUSE Bugzilla

- Alt+U: Use heading for URL

- : Edit local URL

- U: Edit URL

- Shift+N: Extract URLs from note

  - : Open all URLs in subtree

  - Ctrl+U: Open all URLs in subtree (including scrolled branches)

- : Open URL in new tab

- Shift+U: Open URL

-Ctrl+0: Reset selection size

- Ctrl+-: Shrink selection

- Ctrl++: Grow selection

- <: Collapse unselected levels

- Ctrl+<: Collapse one level

-  >: Expand one level

-  S: Scroll branch

-  Shift+O: Sort children backwards

- O: Sort children

- D: Detach

- PgDown: Move down

- PgUp: Move up

- Ctrl+A: Add branch below

- Ctrl+Ins: Add branch below

- Shift+A: Add branch above

- Shift+Ins: Add branch above

- Alt+A: Add branch (insert)

- A: Add branch as child

- C: Add mapcenter

- Del: Delete Selection

- Ctrl+V: Paste

- Ctrl+X: Cut

- Ctrl+C: Copy

- Ctrl+Y: Redo

- Ctrl+Z: Undo

- Ctrl+Q: Exit VYM

- Ctrl+W: Close Map

- Ctrl+P: Print

- Alt+E: Repeat last export (-)

- : Save

- Alt+R: Restore last session

- Ctrl+L: Open

- Ctrl+Shift+N: Copy to new map

- Ctrl+N: New map

### Scope Note Editor:

- Ctrl+Shift+P: Superscript

- Ctrl+Shift+B: Subscript

- Ctrl+U: Underline

- Ctrl+I: Italic

- Ctrl+B: Bold

- Alt+R: Richtext

- Alt+I: Font hint

- Ctrl+V: Paste

- Ctrl+X: Cut

- Ctrl+C: Copy

- Ctrl+A: Select and copy all

- Ctrl+Y: Redo

- Ctrl+Z: Undo

- Ctrl+P: Print

- Alt+X: Export As(ASCII)

- Ctrl+S: Export

- Ctrl+O: Import

## Want to learn

### Learn inskape

#### make vectorial from pictures

Open image (C-i) / (S+A+b) scans 2

## Firefox shortcuts

Keyboard shortcuts resource ([link](https://support.mozilla.org/en-US/kb/keyboard-shortcuts-perform-firefox-tasks-quickly?redirectlocale=en-US&as=u&redirectslug=Keyboard+shortcuts&utm_source=inproduct))

- C+t: new tab

- C+n: new window

- C+k: focus search bar

- C+Shift+v: paste in plain text

- C+w: close tab

- C+Shift+p: new private tab

- C+Shift+t undo close tab

- C+Shift+n undo closed window

- C+1 to 8: select tab 1 to 8

- C+Shift+Y: downloads

- C+h: history

- C+b: bookmarks

- C+Shift+0: library window (bookmarks)

- C+Shift+h: history window

- C+Shift+a: addons

- C+Shift+m: multipanel

- C+Shift+p: page info

- F4: close sidebar

- C+Shift+F4: AllinOneSidebar options

- C+Shift+k: web console

- Shift+F2: developer toolbar

- Shift+J: browser console

- Shift+F5: profiler

- Shift+F4: Scratchpad

- C+u: page source

## Kupfer shortcuts

- S+Space: start

- A+a: alternate activate

- C+,: comma trick

- C+RET: compose command

- C+r: reset all

- C+q: select quit

- C+g: select selected file

- F1: show help

- C+;: show prefferences

- C+s: switch to first pane

===========================================

Other Resources:

Idea for this page is taken from [smalldata.tech](https://smalldata.tech/cheatsheets) and some of the cheatsheets are based on: [Awesome Cheatsheet](https://github.com/detailyang/awesome-cheatsheet)
