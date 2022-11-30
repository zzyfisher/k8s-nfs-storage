在国内搭建k8s集群及其依赖组件间时, 常常会遇到无法下载http://k8s.gcr.io、http://quay.io的镜像。
例如, 在K8S集群中部署nfs-subdir-external-provisioner资源清单时报如下错误, 
```
Failed to pull image "k8s.gcr.io/sig-storage/nfs-subdir-external-provisioner:v4.0.2": 
rpc error: code = DeadlineExceeded desc = failed to pull and unpack image "k8s.gcr.io/sig-storage/nfs-subdir-external-provisioner:v4.0.2": 
failed to resolve reference "k8s.gcr.io/sig-storage/nfs-subdir-external-provisioner:v4.0.2": 
failed to do request: 
Head "https://k8s.gcr.io/v2/sig-storage/nfs-subdir-external-provisioner/manifests/v4.0.2": 
dial tcp 64.233.189.82:443: i/o timeout
```
这是由于国内无法访问k8s.gcr.io, 所以无法拉取下载k8s.gcr.io/sig-storage/nfs-subdir-external-provisioner:v4.0.2镜像.
参考 [用阿里云构建海外镜像](https://blog.csdn.net/weixin_42555971/article/details/125003665) 来解决

