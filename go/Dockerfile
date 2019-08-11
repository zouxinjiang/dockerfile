FROM centos:6.9

RUN mkdir -p /go/src ; \
	mkdir -p /go/bin ; \
	yum install -y wget ; \
	cd /root ;\
	wget https://dl.google.com/go/go1.12.5.linux-amd64.tar.gz ; \
	mkdir /go_env ; \
	tar -zxvf /root/go1* -C /go_env ; \
	rm -rf /root/go1* ; \
	echo -e "GOROOT=/go_env/go \n GOPATH=/go \n GOBIN=\${GOPATH}/bin \n GO111MODULE=auto \n PATH=\${PATH}:\${GOBIN}:\${GOROOT}/bin \n export PATH GOPATH GO111MODULE GOROOT" >> ~/.bash_profile  

ENV GOROOT=/go_env/go GOPATH=/go GO111MODULE=auto
ENV GOBIN=${GOPATH}/bin 
ENV PATH=${PATH}:${GOBIN}:${GOROOT}/bin