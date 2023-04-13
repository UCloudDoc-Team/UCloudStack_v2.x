# 安装Node Exporter

## 使用 wget 下载 Node Exporter

```
wget https://github.com/prometheus/node_exporter/releases/download/v1.5.0/node_exporter-1.5.0.linux-amd64.tar.gz
```

## 使用 tar 解压缩 node_exporter-0.14.0.linux-amd64.tar.gz

```
tar -xvzf ~/Download/node_exporter-1.5.0.linux-amd64.tar.gz
cd node_exporter-1.5.0.linux-amd64
```
## 启动 Node Exporter
我们可以使用 ./node_exporter -h 查看运行选项，./node_exporter 运行 Node Exporter, 如果看到类似输出，表示启动成功
```
INFO[0000] Starting node_exporter (version=0.14.0, branch=master, revision=840ba5dcc71a084a3bc63cb6063003c1f94435a6)  source="node_exporter.go:140"
INFO[0000] Build context (go=go1.7.5, user=root@bb6d0678e7f3, date=20170321-12:13:32)  source="node_exporter.go:141"
INFO[0000] No directory specified, see --collector.textfile.directory  source="textfile.go:57"
INFO[0000] Enabled collectors:                           source="node_exporter.go:160"
.....
INFO[0000] Listening on :9100                            source="node_exporter.go:186"
```