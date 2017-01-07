FROM python:latest

RUN pip install git+https://github.com/scrapy/scrapy.git \
                git+https://github.com/scrapy/scrapyd.git \
                git+https://github.com/scrapy/scrapyd-client.git \
                git+https://github.com/scrapinghub/scrapy-splash.git \
                git+https://github.com/python-pillow/Pillow.git \

    && curl -sSL https://github.com/scrapy/scrapy/raw/master/extras/scrapy_bash_completion -o /etc/bash_completion.d/scrapy_bash_completion \
    && echo 'source /etc/bash_completion.d/scrapy_bash_completion' >> /root/.bashrc \

COPY ./scrapyd.conf /etc/scrapyd/
VOLUME /etc/scrapyd/ /var/lib/scrapyd/
EXPOSE 6800

CMD ["scrapyd"]
