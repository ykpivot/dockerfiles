FROM ubuntu:14.04

# Install.
RUN \
  apt-get update && \
  apt-get -y install build-essential curl ruby ruby-dev libxml2-dev libsqlite3-dev libxslt1-dev libpq-dev libmysqlclient-dev zlib1g-dev wget nfs-common && \
  gem install bosh_cli --no-ri --no-rdoc && \
  wget -O cfcli.tgz "https://cli.run.pivotal.io/stable?release=linux64-binary&source=github" && \
  tar -xvzf cfcli.tgz && \
  chmod 755 cf && \
  mv cf /usr/bin && \
  apt-get -y install git && \
  curl -sL https://deb.nodesource.com/setup_6.x | sudo bash - && \
  apt-get -y install nodejs && \
  wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | apt-key add - && \
  echo "deb http://apt.postgresql.org/pub/repos/apt/ trusty-pgdg main" >> /etc/apt/sources.list.d/postgresql.list && \
  apt-get update && \
  apt-get -y install postgresql-client-9.5 && \
  apt-get install -y \
        python \
        python-dev \
        python-pip \
        python-setuptools \
        groff \
        less && \
  pip install --upgrade awscli && \
  apt-get clean