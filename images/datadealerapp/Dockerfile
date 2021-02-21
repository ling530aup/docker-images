FROM python:3 as clone

RUN mkdir -p /root/.ssh/
ADD id_rsa /root/.ssh/id_rsa
ADD id_rsa.pub /root/.ssh/id_rsa.pub
ADD known_hosts /root/.ssh/known_hosts
RUN chmod -R 600 /root/.ssh/

RUN git clone git@github.com:ling530aup/scrapydatadealer.git

RUN rm -rf /root/.ssh
RUN rm -rf /scrapydatadealer/.git

FROM python:3 as build
COPY --from=clone /scrapydatadealer /scrapydatadealer

RUN pip install PyMySQL
RUN pip install beautifulsoup4
RUN pip install scrapy --default-timeout=900

WORKDIR /scrapydatadealer/com
CMD [ "python3", "/scrapydatadealer/com/Spider_Main.py" ]

# run "docker build -t datadealer ." to build the image


