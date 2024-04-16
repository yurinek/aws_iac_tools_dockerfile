FROM alpine:latest


RUN apk add --no-cache --purge -uU findutils-locate \
npm \
aws-cli \
openssh-client \
openssl-dev \
build-base \
bash \
libffi-dev \
gettext \
libintl \
sysstat \
iotop \
net-tools \
bind-tools \
iputils \
inetutils-telnet \
traceroute \
git \
vim \
screen \
py3-pip \
python3-dev \
py3-virtualenv \
sudo \
rsync \
ca-certificates \
curl \
jq \
wget \
unzip \
&& wget https://releases.hashicorp.com/terraform/1.7.5/terraform_1.7.5_linux_amd64.zip \
&& wget https://get.helm.sh/helm-v3.14.3-linux-amd64.tar.gz \
&& curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl" \
&& tar -zxvf helm-v3.14.3-linux-amd64.tar.gz \
&& rm helm-v3.14.3-linux-amd64.tar.gz \
&& unzip terraform_1.7.5_linux_amd64.zip \
&& rm terraform_1.7.5_linux_amd64.zip \
&& chmod +x linux-amd64/helm \
&& chmod +x kubectl \
&& mv linux-amd64/helm /usr/local/bin/helm \
&& rm -r linux-amd64 \
&& mv kubectl /usr/local/bin \
&& mv terraform /usr/local/bin/ \
&& pip3 install --upgrade pip setuptools \
&& pip3 install --no-cache --upgrade ansible \
&& wget https://get.pulumi.com/releases/sdk/pulumi-v3.111.1-linux-x64.tar.gz \
&& tar -zxvf pulumi-v3.111.1-linux-x64.tar.gz \
&& mv pulumi/* /usr/local/bin/ \
&& rm -r pulumi pulumi-v3.111.1-linux-x64.tar.gz \
&& pip3 install pulumi \
&& pip3 install pulumi_aws \
&& npm install -g aws-cdk \
&& pip3 install --ignore-installed distlib pipenv \
&& npm install --global cdktf-cli@latest \
&& rm -rf /var/cache/apk/* /tmp/* \
&& cdk --version \
&& terraform --version \
&& helm version \
&& kubectl version --client \
&& pulumi version \
&& cdktf --version \
&& aws --version \
&& ansible --version




