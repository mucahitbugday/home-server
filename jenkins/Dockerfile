# Jenkins resmi görüntüsünü temel al
FROM jenkins/jenkins:lts

# Kullanıcıyı root yap
USER root

# Gerekli bağımlılıkları yükle
RUN apt-get update && \
    apt-get install -y \
        apt-transport-https \
        ca-certificates \
        curl \
        gnupg2 \
        software-properties-common

# Docker'ın resmi GPG anahtarını ekle
RUN curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add -

# Docker deposunu ekle
RUN add-apt-repository \
      "deb [arch=amd64] https://download.docker.com/linux/debian \
      $(lsb_release -cs) \
      stable"

# Docker'ı yükle
RUN apt-get update && \
    apt-get install -y docker-ce docker-ce-cli containerd.io

# Jenkins kullanıcısını Docker grubuna ekle
RUN usermod -aG docker jenkins

# Varsayılan kullanıcıyı geri döndür
USER jenkins

