ARG FROM_IMAGE
ARG IMAGE_NAME
ARG IMAGE_TAG
ARG UNREAL_VERSION

FROM ${FROM_IMAGE}

LABEL Maintenair="Akhoriz"

RUN apt-get install -y --no-install-recommends \
    build-essential \
    wget \
    unzip 


RUN wget https://codeload.github.com/EpicGames/UnrealEngine/zip/refs/tags/$UNREAL_VERSION-release?token=AIU4ME5B5JGUBZZCCE4WO6DC2RODG -O /tmp/server.zip

RUN unzip /tmp/server.zip -d server
RUN cd server
RUN ./Setup.sh
RUN ./GenerateProjectFiles.sh
RUN make UnrealMultiUserServer
