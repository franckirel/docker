FROM avastsoftware/perl-mechanize-phantomjs
MAINTAINER Franck <fmoube@internap.com>


# install subversion client
RUN apt-get -y update && apt-get install -y wget perl subversion php5-cli php5-curl sshpass libwww-mechanize-perl perl libssl-dev subversion traceroute nmap vim-nox ipcalc libxml-simple-perl &&  \
mkdir -p /TMS


RUN cpan force install NetAddr::IP Data::Validate::IP Net::OpenSSH RT::Client::REST::Ticket WWW::Mechanize::Cached Crypt::SSLeay \
    Net::SSH::Expect Frontier::Client CHI Net::Ping  Net::Telnet XML::Simple HTML::TreeBuilder HTML::TableExtract \
    Getopt::Long Class::Date URI Net::DNS Term::Menu JSON \
    URI::QueryParam Net::IP RT::Client::REST MIME::Head Regexp::Common \
    Term::ReadLine::Perl YAML IPC::Run Net::SSL XML::Simple Frontier::Client Net::SSLeay


ENV svn_user tms
ENV svn_pass DlEFNsmvo7FB6

WORKDIR /TMS

RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/APC
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/Cluster
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/cPanel
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/DisableReverse
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/Fantastico
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/iSGI
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/iWebDNS
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/Munin
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/Passwords
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/rDNS
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/Scripts
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/StaticRoutes
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/Switch
RUN svn co --username=$svn_user --password=$svn_pass --non-interactive --trust-server-cert https://svn-operations.corp.iweb.com/svn/Blacklist


# export my repository
#RUN svn export --username=myUserName --password=myPassword http://subversion.myserver.com/path/to/directory

# further commands, e.g. on container start run a file just downloaded from the repository
#CMD ["/bin/bash", "path/to/file.sh"]
