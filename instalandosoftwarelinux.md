#!/bin/bash

apt-get update

apt-get upgrade -y

echo "instalando samba"

apt-get install samba -y

echo "samba instalado

echo "instalando unzip"

apt-get install unzip -y

echo "instalando apache2"

apt-get install apache2 -y

echo "apache instalado"