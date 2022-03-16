# Etcd-Certificate-updation #



Got a support ticket with description stating that a client certificate used to authenticate to the apiserver is expiring in less than 7 days(KubeClientCertificateExpiration)

First we need to login using ssh to Jump hostserver

Then we will have to login to each controlplane nodes and we need to login to Jump host and then check the status of certificate expiry


'kubectl certs check-expiration'

We noticed that 3 certificate are going to expire by 17March 2022


'kubeadm certs renew  etcd-server'

kubeadm certs renew  etcd-peer

kubeadm certs renew  etcd-health-checker

after this again checked whether certificates are renewed it using "kubectl certs check-expiration"  and confirmed it worked
