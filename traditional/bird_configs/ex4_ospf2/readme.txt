1. copy the bird config files

sudo docker cp  R_A.conf R_A:/etc/bird.conf
sudo docker cp  R_B.conf R_B:/etc/bird.conf
sudo docker cp  R_C.conf R_C:/etc/bird.conf
sudo docker cp  R_D.conf R_D:/etc/bird.conf
sudo docker cp  R_E.conf R_E:/etc/bird.conf
sudo docker cp  R_F.conf R_F:/etc/bird.conf
sudo docker cp  R_G.conf R_G:/etc/bird.conf
sudo docker cp  R_H.conf R_H:/etc/bird.conf
sudo docker cp  R_I.conf R_I:/etc/bird.conf
sudo docker cp  R_J.conf R_J:/etc/bird.conf


2. start the bird daemon on each router

sudo docker exec -it R_A  sh
bird -c /etc/bird.conf

Repeat the same for all other routers