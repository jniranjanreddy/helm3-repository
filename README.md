# helm3-repository


```
[root@minikube01 jnr]# helm create gitrepotest2
Creating gitrepotest2

[root@minikube01 jnr]# cd gitrepotest2
[root@minikube01 gitrepotest2]# ll
total 8
drwxr-xr-x. 2 root root    6 Jun 24 12:29 charts
-rw-r--r--. 1 root root 1148 Jun 24 12:29 Chart.yaml
drwxr-xr-x. 3 root root  162 Jun 24 12:29 templates
-rw-r--r--. 1 root root 1879 Jun 24 12:29 values.yaml

[root@minikube01 gitrepotest2]# pwd
/jnr/gitrepotest2
[root@minikube01 gitrepotest2]# cd ..

[root@minikube01 jnr]# ls
aws-eks  gitrepotest  gitrepotest2  helm3-repository
[root@minikube01 jnr]# cd helm3-repository/

[root@minikube01 helm3-repository]# ll
total 12
-rw-r--r--. 1 root root 3768 Jun 24 12:20 gitrepotest-0.1.0.tgz
-rw-r--r--. 1 root root  415 Jun 24 12:21 index.yaml
-rw-r--r--. 1 root root   19 Jun 24 12:16 README.md

[root@minikube01 helm3-repository]# helm package /jnr/gitrepotest2
Successfully packaged chart and saved it to: /jnr/helm3-repository/gitrepotest2-0.1.0.tgz

[root@minikube01 helm3-repository]# ll
total 16
-rw-r--r--. 1 root root 3768 Jun 24 12:20 gitrepotest-0.1.0.tgz
-rw-r--r--. 1 root root 3756 Jun 24 12:31 gitrepotest2-0.1.0.tgz
-rw-r--r--. 1 root root  415 Jun 24 12:21 index.yaml
-rw-r--r--. 1 root root   19 Jun 24 12:16 README.md
[root@minikube01 helm3-repository]# helm repo index .

[root@minikube01 helm3-repository]# cat index.yaml
apiVersion: v1
entries:
  gitrepotest:
  - apiVersion: v2
    appVersion: 1.16.0
    created: "2021-06-24T12:32:08.87824264-04:00"
    description: A Helm chart for Kubernetes for github
    digest: d9b39d709d8e2340db9edda371e736686c781cc8afed0d05254977ae51d4cf8d
    name: gitrepotest
    type: application
    urls:
    - gitrepotest-0.1.0.tgz
    version: 0.1.0
  gitrepotest2:
  - apiVersion: v2
    appVersion: 1.16.0
    created: "2021-06-24T12:32:08.879784899-04:00"
    description: A Helm chart for Kubernetes
    digest: 591b93120be6810ad012ca598e398ce5bb4bb6597a3196556c6045726b3c54f2
    name: gitrepotest2
    type: application
    urls:
    - gitrepotest2-0.1.0.tgz
    version: 0.1.0
generated: "2021-06-24T12:32:08.876366866-04:00"
[root@minikube01 helm3-repository]#

[root@minikube01 helm3-repository]# helm search repo
NAME                            CHART VERSION   APP VERSION     DESCRIPTION
helm3-repository/gitrepotest    0.1.0           1.16.0          A Helm chart for Kubernetes for github


[root@minikube01 helm3-repository]# helm repo update
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "helm3-repository" chart repository
Update Complete. ⎈Happy Helming!⎈

[root@minikube01 helm3-repository]# helm search repo
NAME                            CHART VERSION   APP VERSION     DESCRIPTION
helm3-repository/gitrepotest    0.1.0           1.16.0          A Helm chart for Kubernetes for github
helm3-repository/gitrepotest2   0.1.0           1.16.0          A Helm chart for Kubernetes


```
