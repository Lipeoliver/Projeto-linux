#!/bin/bash
echo "criando diretorios"

mkdir /adm
mkdir /sec
mkdir /ven
mkdir /publico

echo "criando usuarios"

echo "grupo 1"

echo "carlos:123:1002:1002:carlos:/home/carlos:/bin/bash" | newusers
echo "maria:123:1003:1003:maria:/home/maria:/bin/bash" | newusers
echo "joao:123:1004:1004:joao:/home/joao:/bin/bash" | newusers

echo "grupo 2 "

echo "debora:123:1005:1005:debora:/home/debora:/bin/bash" | newusers
echo "sebastiana:123:1006:1006:sebastiana:/home/sebastiana:/bin/bash" | newusers
echo "roberto:123:1007:1007:roberto:/home/roberto:/bin/bash" | newusers

echo "grupo 3"

echo "josefina:123:1008:1008:josefina:/home/josefina:/bin/bash" | newusers
echo "amanda:123:1009:1009:amanda:/home/amanda:/bin/bash" | newusers
echo "rogerio:123:10010:1010:rogerio:/home/rogerio:/bin/bash" | newusers

echo "usuarios criados"

echo "criando grupos"

groupadd GRP_ADM
groupadd GRP_VEN
groupadd GRP_SEC

echo "grupos criados"

echo "Adicionando Usuarios aos grupos "

usermod -G GRP_ADM carlos
usermod -G GRP_ADM maria
usermod -G GRP_ADM joao

usermod _G GRP_VEN debora
usermod _G GRP_VEN sebastiana
usermod _G GRP_VEN roberto

usermod _G GRP_SEC josefina
usermod _G GRP_SEC amanda
usermod _G GRP_SEC rogerio

echo "Usuarios Adicionados"

echo "Colocando dono no diretorio"

chown root:GRP_ADM /adm
chown root:GRP_VEN /ven
chown root:GRP_SEC /sec
chown root /publico

echo "mudando permissoes"

chmod 777 /publico
chmod 770 /ven
chmod 770 /adm
chmod 770 /sec

echo "Fim"

