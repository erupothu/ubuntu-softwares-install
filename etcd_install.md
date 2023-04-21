
#### From APT

$ sudo apt-get update  
$ sudo apt-get install etcd  
$ cd etcd  
$ sudo mv etcd etcdctl etcdutl /usr/local/bin/  
$ sudo service etcd status  
$ etcd --version  
$ etcdctl version  
$ etcdutl version  
$ etcdctl put /home/admin/keys/key1 harish  
$ etcdctl get /home/admin/keys/key1  

#### From WGET

$ wget https://github.com/etcd-io/etcd/releases/download/v3.5.6/etcd-v3.5.6-linux-amd64.tar.gz  
$ tar xvf etcd-v3.5.6-linux-amd64.tar.gz  
$ mv etcd-v3.5.6-linux-amd64 etcd  
$ $ cd etcd  
$ sudo mv etcd etcdctl etcdutl /usr/local/bin/  
$ etcd --version  
$ etcdctl version  
$ etcdutl version  
$ etcdctl put /home/admin/keys/key1 harish  
$ etcdctl get /home/admin/keys/key1  


#### From Source

$ sudo apt-get install golang git -y  
$ git clone https://github.com/etcd-io/etcd.git  
$ cd etcd  
$ ./scripts/build.sh  
$ export PATH="$PATH:`pwd`/bin"  
$ etcd --version  

#### etcd manager [https://etcdmanager.io/]  

$ snap install etcd-manager  
open etcd manager tool and configure connections  
  Profile: local-etcd  
  Host: 127.0.0.1  
  Port: 2379  
  
#### etcd manager from source (Vue.js frontend)  

$ git clone https://github.com/i-Cell-Mobilsoft-Open-Source/etcdmanager.git  
$ npm install etcd-manager  
$ npm rebuild --target=ELECTRON_VERSION --runtime=electron --dist-url=https://atom.io/download/electron  
$ yarn list electron  
$ yarn electron:serve  



  


