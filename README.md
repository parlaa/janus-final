Ive been searching for janus-gateway docker compose for a while, as i needed it to be easily deployed and moved from one instance to other, but all composes ive found were not working or were outdated, as the images they used recieved no updates. For more flexible castomization and configuration i used volumes to easily access the configs that may be changed very frequently. Below ill describe the structure of my repo and the installation process.
---STRUCTURE---
docker-compose.yml - default setup, using the canyanio image for janus-gateway basic installation with all needed packages, nothing may be changed except if u want to specify the ports
etc/janus/ - contains config files for janus, ive added not all of them, as other configs i dont use, u may copy them from the https://github.com/meetecho/janus-gateway.git repo *** u must change the configs for your setups 
config/janus/ - contains three repos: plugins, transports, events. All the plugins are activated and u just need to disable which u are not going to use in etc/config/janus.jcfg
share/janus/ - just some html's and js's that were taken from the https://github.com/meetecho/janus-gateway.git repo, ive made it as a volume too, in case ill need something to be configured.
---
