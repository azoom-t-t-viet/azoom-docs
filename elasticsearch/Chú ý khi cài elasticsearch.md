Khi cài xong elastic search, muốn truy cập thông qua ip hoặc cluster name thì cần cài đặt bên dưới:

```cmd
$ sudo vim /etc/elasticsearch/elasticsearch.yml
```
và sửa `network.host` thành ip hoặc tên cluster name

Ví dụ:

```
network.host = 192.168.0.0.23

hoặc

network.host = elasticsearch-cluster
```
