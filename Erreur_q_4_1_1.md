## 4.1. Résolution des problèmes de la VM et préparation



1.	Redirection vers les archives (Vault) de CentOS :
```bash 
sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-Base.repo
sed -i 's/#baseurl/baseurl/g' /etc/yum.repos.d/CentOS-Base.repo
sed -i 's/mirror.centos.org/vault.centos.org/g' /etc/yum.repos.d/CentOS-Base.repo
yum clean all
``` 
2. Installation des outils en ignorant les serveurs morts (Hortonworks) :
```bash 

yum install python-pip nano --disablerepo="HDP*" --disablerepo="ambari*" --disablerepo="ius"
```

3. Installation des bibliothèques Python nécessaires pour exécuter MapReduce :
```bash
pip install pathlib PyYAML==5.4.1 mrjob==0.7.4
```

Solution proposée par : Ibrahim RAHMANI 