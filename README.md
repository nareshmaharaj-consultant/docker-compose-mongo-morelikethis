# docker-compose-mongo-morelikethis

Usage:

```docker-compose up -d```

Add some sample messages in the namespace ```product.items``` you can change this to your own namespace as desired.

 ```mongosh```
 <br>```use product```
 <br>```db.items.insertOne({a:1})```
 
In a new window
<br><br>```docker run -it --rm --network mongo-morelikethis-network contactnkm/morelikethis bash```

Produce sample messages
<br><br>
```mongodb-schema mongo-net:27017 product.items | morelikethis | mgeneratejs -n 100 | mongoimport --host mongo-net --port 27017 -d productmake -c items```


