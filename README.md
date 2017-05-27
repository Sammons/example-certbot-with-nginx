This is a sample docker-compose.yml that stands up a web app with letsencrypt SSL.

It uses certbot and docker compose v3 syntax to work.

To test this out, I deployed a 512mb 1cpu node on digital ocean with the pre-baked image for docker, and initialized a docker swarm on it. This is not an example of good scalable swarm build.


Steps to get going:

1) clone this repo
2) change the example.io and you@whatever.io values to your own values
3) update your nameservers to point the values you just set to the machine you are docker-compose up'ing on
4) confirm with `dig` that the values you put in VIRTUAL_HOST and LETSENCRYPT_HOST are resolvable from the machine you are running this on. Certbot (letsencrypt) will need to self-resolve that you own this DNS, so the DNS has to be up to date to start
5) `docker-compose up -d` 
6) enjoy! If it isn't behaving try `docker-compose logs letsencrypt` to see any issues


If there were a license here, it would be MIT



