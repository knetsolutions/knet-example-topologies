1. copy the bird config files

sudo docker cp  R1.conf R1:/etc/bird.conf
sudo docker cp  R2.conf R2:/etc/bird.conf
sudo docker cp  RA1.conf RA1:/etc/bird.conf
sudo docker cp  RA2.conf RA2:/etc/bird.conf
sudo docker cp  RB1.conf RB1:/etc/bird.conf
sudo docker cp  RB2.conf RB2:/etc/bird.conf



2. start the bird daemon on each router

sudo docker exec -it R1  sh
bird -c /etc/bird.conf

Repeat the same for all other routers