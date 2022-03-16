## Etcd-Certificate-updation ##
---

Got a support ticket with description stating that a client certificate used to authenticate to the apiserver is expiring in less than 7 days(KubeClientCertificateExpiration)

* First we need to login using ssh to Jump hostserver

* Then we will have to login to each controlplane nodes and then check the status of certificate expiry

   'kubectl certs check-expiration'

* We noticed that 3 certificates (etcdserver,etcd-peer,etcd-health-checker) are going to expire by 17 March 2022


   'kubeadm certs renew  etcd-server'

   'kubeadm certs renew  etcd-peer'

   'kubeadm certs renew  etcd-health-checker'

* After this again checked whether certificates are renewed it using 'kubectl certs check-expiration'  and confirmed it worked
