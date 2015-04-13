# Pull base image
FROM ubuntu:14.04.2

# Installation instructions: http://pngu.mgh.harvard.edu/~purcell/plink/download.shtml#latest

# Environment variables
ENV PLINK_VERSION       1.07
ENV PLINK_HOME          /usr/local/plink
ENV PATH                $PLINK_HOME:$PATH


RUN DEBIAN_FRONTEND=noninteractive apt-get install -y unzip wget && \
    wget http://pngu.mgh.harvard.edu/~purcell/plink/dist/plink-$PLINK_VERSION-x86_64.zip && \
    unzip plink-$PLINK_VERSION-x86_64.zip -d /usr/local/ && \
    rm plink-$PLINK_VERSION-x86_64.zip && \
    cd /usr/local && \
    ln -s plink-$PLINK_VERSION-x86_64 $PLINK_HOME && \
    DEBIAN_FRONTEND=noninteractive apt-get autoremove -y unzip wget && \
    rm -rf /var/lib/apt/lists/*



# Set the default action to print plink's options 
# TODO: create an alias for plink so that --noweb is a default option
# TODO: write example: plink --noweb --file /usr/local/plink/test
CMD ["plink --noweb"]


# FIXME: not using the --noweb option will hang plink:
# 
# @----------------------------------------------------------@
# |        PLINK!       |     v1.07      |   10/Aug/2009     |
# |----------------------------------------------------------|
# |  (C) 2009 Shaun Purcell, GNU General Public License, v2  |
# |----------------------------------------------------------|
# |  For documentation, citation & bug-report instructions:  |
# |        http://pngu.mgh.harvard.edu/purcell/plink/        |
# @----------------------------------------------------------@
# 
# Web-based version check ( --noweb to skip )
# Connecting to web...


# While investigating the issue with strace, the problem appears to be related to a DNS issue:
#
# write(3, "Web-based version check ( --nowe"..., 44) = 44
# write(1, "Web-based version check ( --nowe"..., 44Web-based version check ( --noweb to skip )
# ) = 44
# write(3, "Connecting to web... ", 21)   = 21
# write(1, "Connecting to web... ", 21Connecting to web... )   = 21
# socket(PF_INET, SOCK_STREAM, IPPROTO_IP) = 4
# connect(4, {sa_family=AF_INET, sin_port=htons(80), sin_addr=inet_addr("132.183.161.22")}, 16) = 0
# sendto(4, "GET /~purcell/plink/version2.txt"..., 89, 0, NULL, 0) = 89
# recvfrom(4, 

# So plink tries to connect to 132.183.161.22 (abilene.mgh.harvard.edu) but apparently the file
# has moved to 155.52.206.11 (pngu.mgh.harvard.edu)
#
# The following works:
# wget http://pngu.mgh.harvard.edu/~purcell/plink/version2.txt)

# We could setup a redirect IP route, but this isn't trival from Docker as iptable does not work
# by default from within a container.
#
# root@c5c368a98c93:/# iptables -t nat -A OUTPUT -d 132.183.161.22 -j DNAT --to-destination 155.52.206.11 
# iptables v1.4.21: can't initialize iptables table `nat': Permission denied (you must be root)
# 
# http://superuser.com/questions/681705/using-iptables-to-redirect-ip-address
# http://stackoverflow.com/questions/24889346/sed-how-to-uncomment-a-line-that-contains-a-specific-string-inline-editing
# http://superuser.com/questions/684652/iptables-gives-me-the-error-cant-initialize-iptables-nat


# This thread recommands using PLINK/SEQ instead for annotation functions
# http://seqanswers.com/forums/showthread.php?t=36214

