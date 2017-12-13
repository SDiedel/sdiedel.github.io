# How to PUT a base64 encoded string into etcd key with cURL

When using cURL, use this command (the order is very(!) important!!!):

`curl -XPUT --data-urlencode value="base64 encoded string" http://127.0.0.1:2379/v2/keys/...`
