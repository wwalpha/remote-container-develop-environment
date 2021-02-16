FROM amazonlinux

# commons
RUN yum install -y git unzip jq && \
  # node.js
  curl -sL https://rpm.nodesource.com/setup_14.x | bash - && \
  yum install -y nodejs && node -v && \
  # yarn
  npm install -g yarn && yarn -v && \
  # global libraries
  npm install -g typescript ts-node && \
  # docker
  amazon-linux-extras enable docker && \
  yum clean metadata && \
  yum install -y docker && docker -v && \
  # enable docker
  systemctl enable docker && \
  # aws cli
  curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip" && \
  unzip awscliv2.zip && ./aws/install && aws --version

CMD [ "/sbin/init" ]
