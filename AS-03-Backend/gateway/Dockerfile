FROM openresty/openresty:alpine-fat

# Install dependencies
RUN opm get ledgetech/lua-resty-http
RUN opm get jkeys089/lua-resty-hmac  
RUN opm get openresty/lua-resty-string
RUN opm get cdbattags/lua-resty-jwt
RUN opm get openresty/lua-resty-limit-traffic

# Copy custom nginx config and lua scripts  ← ADD THESE
COPY nginx.conf /usr/local/openresty/nginx/conf/nginx.conf
COPY lua/ /usr/local/openresty/nginx/lua/

EXPOSE 80

CMD ["/usr/local/openresty/bin/openresty", "-g", "daemon off;"]