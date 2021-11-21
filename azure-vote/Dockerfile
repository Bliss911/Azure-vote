# Pull the base image
FROM tiangolo/uwsgi-nginx-flask:python3.6
# Install depndencies 
RUN pip3 install redis
RUN pip3 install opencensus
RUN pip3 install opencensus-ext-azure
RUN pip3 install opencensus-ext-flask
RUN pip3 install opencensus-ext-logging
RUN pip3 install flask

RUN echo user=root >>  /etc/supervisor/supervisord.conf
CMD ["/usr/bin/supervisord","-n"]
# Copy the content of the current directory to the /app of the container
ADD . /app
RUN pip install -r requirements.txt
