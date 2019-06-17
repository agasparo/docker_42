FROM debian

RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install ca-certificates wget openssh-server postfix -y

EXPOSE 80
EXPOSE 443

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
RUN chmod 755 script.deb.sh
RUN ./script.deb.sh
RUN rm -rf script.deb.sh
RUN apt-get install gitlab-ce -y
RUN gitlab-ctl reconfigure
