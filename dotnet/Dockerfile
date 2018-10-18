FROM matissehack/tiny-teams:base

ENV DOTNET_VERSION 2.1
# Before installing .NET, you'll need to register the Microsoft key, register the product repository,
# and install required dependencies. This only needs to be done once per machine.
# References: https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-current
RUN curl -fsSLO --compressed https://packages.microsoft.com/config/ubuntu/$UBUNTU_VERSION/packages-microsoft-prod.deb \
  && dpkg -i packages-microsoft-prod.deb \
  && rm -f packages-microsoft-prod.deb
RUN apt-get update \
  && apt-get -y --no-install-recommends install \
    dotnet-runtime-$DOTNET_VERSION \
  && rm -rf /var/lib/apt/lists/*
  