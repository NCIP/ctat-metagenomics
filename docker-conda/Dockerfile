FROM ubuntu
RUN apt-get -y update
RUN apt-get install -y wget gzip zip bzip2 python
RUN wget https://repo.continuum.io/miniconda/Miniconda2-latest-Linux-x86_64.sh
RUN echo "yes\nyes\n" > conda_inst_stdin.txt
RUN bash Miniconda2-latest-Linux-x86_64.sh < conda_inst_stdin.txt
ENV PATH /root/miniconda2/bin:$PATH
RUN conda config --add channels r
RUN conda config --add channels bioconda
RUN conda list
ADD . /data
WORKDIR /data
RUN conda install -y ctat-metagenomics
#RUN cp -r /root/miniconda2/pkgs/ctat-metagenomics-1.0.1-py27_1/share/ctat-metagenomics-1.0.1-1/* /root/miniconda2/bin/
