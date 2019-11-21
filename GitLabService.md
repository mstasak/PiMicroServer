GitLab CE provides a git server for SCM.

I installed using instructions from [here](https://howtoraspberrypi.com/private-git-raspberry-gitlab/).

```shell

#increase swapfile size, or gitlab-ctl reconfigure may exhaust RAM.
sudo vi /etc/init.d/dphys-swapfile
(replace CONF_SWAPSIZE=100 with CONF_SWAPSIZE=2048, around line 13)
Esc,Z,Z (three keys, skit the commas, to save and exit vi)
sudo /etc/init.d/dphys-swapfile stop
sudo /etc/init.d/dphys-swapfile start

sudo apt install curl openssh-server ca-certificates postfix apt-transport-https

curl https://packages.gitlab.com/gpg.key | sudo apt-key add -

sudo curl -o /etc/apt/sources.list.d/gitlab_ce.list "https://packages.gitlab.com/install/repositories/gitlab/raspberry-pi2/config_file.list?os=debian&dist=jessie"

sudo apt-get update
 
sudo apt-get install gitlab-ce

#reconfigure gitlab ce for reduced resource usage
sudo vi /etc/gitlab/gitlab.rb
change: unicorn['worker_processes'] = 2
change: sidekiq['concurrency'] = 9//
add: prometheus['monitoring'] = false
(save)

sudo gitlab-ctl reconfigure

```

Then access your GitLab server at http://localhost

Watching reconfigure run, I believe this is using a PostgreSQL back end, which is nice but perhaps resource heavy for a Pi.

TODO: Investigate lightweight GitLab back end alternatives (SQLite?)

