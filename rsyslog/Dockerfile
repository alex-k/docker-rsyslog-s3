FROM panoptix/rsyslog

RUN apt-get update && apt-get -y install curl

COPY s3cmd-1.6.0.tar.gz  /tmp

RUN sudo apt-get -y install python-setuptools \
      && cd /tmp \
      && tar xvfz s3cmd-1.6.0.tar.gz \
      && cd s3cmd-1.6.0 \
      && sudo python setup.py install

COPY logrotate.conf /etc/logrotate.conf
COPY docker.conf /etc/logrotate.d/rsyslog
COPY .s3cfg /root/.s3cfg
COPY logrotate.stop /etc/local.d/logrotate.stop


