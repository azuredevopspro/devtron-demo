FROM tiangolo/uwsgi-nginx-flask:python3.8-alpine
RUN apk --update add bash nano
ENV STATIC_URL /static
ENV STATIC_PATH /var/www/app/static
COPY azure-vote-app/azure-vote/requirements.txt /var/www/requirements.txt
RUN pip install -r /var/www/requirements.txt
ADD azure-vote-app/azure-vote/azure-vote /app