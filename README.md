After first `docker compose up`, you need run this (replace mongodb_main with actual hostname):

```shell
hostname="mongodb_main"
mongosh mongodb://${hostname}/ --eval "rs.initiate({ _id: \"rs0\", members: [{ _id: 0, host: \"${hostname}\" }] })"
```
