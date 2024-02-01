FROM debian
RUN apt update && apt upgrade -y
RUN apt install gcc -y
RUN mkdir ~/test
COPY . ~/test
RUN cp /root/test/test.c /root/test.c
# RUN gcc ~/test/test.c -o ~/app
# CMD ~/app
CMD ls -lah ~