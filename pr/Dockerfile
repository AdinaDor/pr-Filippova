FROM ubuntu

LABEL author="Filippova Daria"

ENV TZ=Europe/Moscow
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update
RUN apt-get install qt5-default -y
RUN apt-get install qtbase5-dev -y
RUN apt-get install qt5-qmake
RUN apt-get install build-essential -y

COPY . /filippova_221-353

# Установка рабочей директории
WORKDIR /filippova_221-353

# Компиляция проекта
RUN qmake
RUN make

# Указание, что контейнер будет служить исполняемым файлом с именем hallServer
CMD ["./hallServer"]