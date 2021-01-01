FROM ubuntu:18.04

RUN apt-get update

RUN apt-get install -y wget software-properties-common gnupg2 winbind xvfb

RUN dpkg --add-architecture i386 && \
	apt-get update && \
	apt-get install -y wine32

COPY gcalw3.exe /deployments/app.exe

COPY MFC42.dll /root/.wine/drive_c/windows/system32/MFC42.dll

RUN mkdir -p WebPages /

EXPOSE 3683

CMD xvfb-run wine /deployments/app.exe
