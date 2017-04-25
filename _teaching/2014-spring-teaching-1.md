---
title: "install Monaco font like Texmate on gedit (Linux)"
collection: teaching
type: ""
permalink: /teaching/2014-spring-teaching-1
venue: ""
date: 2017-04-24
location: ""
---

Find on rogerleite GitHub; Very nice work !

#!/bin/bash

#script extraido de: http://paulocassiano.wordpress.com/2008/08/29/deixando-o-gedit-com-a-cara-do-textmate/
#tip for better "resolution" here: http://blog.siverti.com.br/2008/05/22/fonte-monaco-no-ubuntugedit/

cd /usr/share/fonts/truetype/

#TODO: put validation if folder already exists
sudo mkdir ttf-monaco

cd ttf-monaco/

sudo wget http://www.gringod.com/wp-upload/software/Fonts/Monaco_Linux.ttf

#create an index of X font files in a directory
sudo mkfontdir

#go to parent folder /usr/share/fonts/truetype
cd ..

fc-cache