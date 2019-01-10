FROM python:3-alpine3.8
RUN apk --update --no-cache add curl
RUN pip install --upgrade pip setuptools awscli
RUN rm -r /root/.cache

RUN mkdir .kube
RUN curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.10.3/2018-07-26/bin/linux/amd64/aws-iam-authenticator
RUN curl -o kubectl https://amazon-eks.s3-us-west-2.amazonaws.com/1.10.3/2018-07-26/bin/linux/amd64/kubectl
RUN curl -s https://api.github.com/repos/kubernetes-sigs/kustomize/releases/latest |\
  grep browser_download |\
  grep linux |\
  cut -d '"' -f 4 |\
  xargs curl -O -L
RUN mv kustomize_*_linux_amd64 kustomize
RUN chmod +x ./aws-iam-authenticator
RUN chmod +x ./kubectl
RUN chmod +x ./kustomize
RUN cp ./aws-iam-authenticator /bin/aws-iam-authenticator && export PATH=$HOME/bin:$PATH
RUN cp ./kubectl /bin/kubectl && export PATH=$HOME/bin:$PATH
RUN cp ./kustomize /bin/kustomize

