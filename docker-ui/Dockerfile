FROM joxit/docker-registry-ui:latest

#execute docker ui 
RUN sh /docker-entrypoint.sh

#as joxit/docker-registry-ui:latest this use alpine linux server so use apk as a pakage manager 
RUN apk update && apk add nginx && rm -rf /var/cache/apk/* 


#copy cert and key 
COPY cert.pem   /etc/nginx/ssl/cert.pem
COPY key.pem    /etc/nginx/ssl/key.pem


#this line replace defualt.conf with nginx.conf
COPY nginx.conf /etc/nginx/conf.d/default.conf


#for https 

EXPOSE 443 

#command 

ENTRYPOINT ["/docker-entrypoint.sh"]

CMD ["nginx" , "-g" , "daemon off;"]