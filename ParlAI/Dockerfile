#Dockerfile for ParlAI + pytorch + RUS locale

From ubuntu:17.10

RUN apt update
RUN apt install build-essential cmake make wget git -y
RUN apt install python3.6 python3.6-dev -y
RUN wget https://bootstrap.pypa.io/get-pip.py
RUN python3.6 get-pip.py

WORKDIR /service

RUN pip3 install https://download.pytorch.org/whl/cu80/torch-0.4.1-cp36-cp36m-l$
RUN pip3 install torchvision
RUN pip3 install regex scipy scikit-learn pexpect

RUN git clone https://github.com/facebookresearch/ParlAI.git /service/ParlAI
RUN cd /service/ParlAI; pip3 install ./requirements.txt; echo "" > README.md; p$

RUN apt-get install -y locales
RUN locale-gen en_US
RUN locale-gen en_US.UTF-8
RUN locale-gen ru_RU
RUN locale-gen ru_RU.UTF-8
RUN update-locale

RUN echo "LC_ALL=en_US.UTF-8" >> /etc/environment
RUN echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen
RUN echo "LANG=en_US.UTF-8" > /etc/locale.conf
