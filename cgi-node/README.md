
Build and run docker
```
docker build -t cgi-node .
docker run -it --rm -p 8080:80 -v "$(pwd)/vuln:/var/www/html" --entrypoint=/bin/bash cgi-node
```

Start apache server
```
apache2ctl start
```

Set executable permission on `cgi-node.js`
```
chmod +x /var/www/html/cgi-bin/cgi-node.js
```

If server errors, review log
```
tail /var/log/apache2/error.log
```

Test: http://localhost:8080/test/CgiNodeInfo.jss