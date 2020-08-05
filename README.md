### Managing Kiam Certs using cert-manager (POC)


* setup issuer to issue selfsigned CA

```
kubectl apply -f kiam-ca-issuer.yaml
```

* issue ca certificate

```
kubectl get kiam-ca-certificate.yaml
```

* issue kiam server certificate

```
kubectl apply -f server-certificate.yaml
```

* issue kiam agent certificate

```
kubectl apply -f agent-certificate.yaml
```

* check all issuers

```
$ kubectl get issuers -n kube-system
NAME      READY   AGE
kiam      True    37m
kiam-ca   True    37m
```

* check all certificate

```
$ kubectl get certificate -n kube-system
NAME              READY   SECRET            AGE
kiam-agent-tls    True    kiam-agent-tls    38m
kiam-ca-tls       True    kiam-ca-tls       38m
kiam-server-tls   True    kiam-server-tls   38m
```