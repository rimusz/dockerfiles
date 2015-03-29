FROM phusion/baseimage:latest

RUN apt-get update
RUN apt-get install -y mc

# Set correct environment variables.
ENV HOME /root

# enable ssh server
RUN rm -f /etc/service/sshd/down

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]

##
ADD ./ssh/config /root/.ssh/
ADD ./00_host_keys.sh /etc/my_init.d/00_host_keys.sh
RUN chmod 755 /etc/my_init.d/00_host_keys.sh

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 22
