FROM ubuntu:latest

ENV DEBIAN_FRONTEND=noninteractive
RUN  apt-get update -y && apt-get install -y software-properties-common build-essential libffi-dev libssl-dev python3-dev python3-pip git systemd
RUN pip3 install setuptools && pip3 install ansible

WORKDIR /src/tests/
ENTRYPOINT echo '[local]\nlocalhost ansible_python_interpreter=/usr/bin/python3 ansible_connection=local ansible_host=127.0.0.1' > host.ini && ansible-playbook --connection=local -v --inventory host.ini tests_*.yml
