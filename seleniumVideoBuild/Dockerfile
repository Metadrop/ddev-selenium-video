#ddev-generated
ARG BASE_IMAGE
FROM $BASE_IMAGE

USER root

ARG username
ARG uid
ARG gid
RUN userdel -r seluser
RUN (groupadd --gid $gid "$username" || groupadd "$username" || true) && (useradd  -l -m -s "/bin/bash" --gid "$username" --comment '' --uid $uid "$username" || useradd  -l -m -s "/bin/bash" --gid "$username" --comment '' "$username" || useradd  -l -m -s "/bin/bash" --gid "$gid" --comment '' "$username" || useradd -l -m -s "/bin/bash" --comment '' $username )

# Add sudo and sudoers in manner similar to other ddev containers
RUN apt update --fix-missing; apt install -y sudo; mkdir /etc/sudoers.d; echo "ALL ALL=NOPASSWD: ALL" > /etc/sudoers.d/ddev-selenium && chmod 440 /etc/sudoers.d/ddev-selenium

RUN mkdir --parents /home/$username/reports && chown --recursive $username:$username /home/$username

# Setup ddev user name and folder.
USER $username
WORKDIR /videos
