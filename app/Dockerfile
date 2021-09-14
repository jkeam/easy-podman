FROM centos:centos8
RUN yum install python3 -y
USER nobody
ENV APP_HOME /app
WORKDIR $APP_HOME
COPY . ./
CMD ["python3", "-m", "http.server", "8000", "--bind", "0.0.0.0"]
