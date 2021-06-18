#1 Running a command
Build a docker image using Dockerfile in the "." (current) directory
	docker build -f Dockerfile -t jeetu-debian-image .
Check that the image is created
	docker image ls
Create and run a container using the image. "--rm" will delete the created container after the run is completed
	docker run --rm jeetu-debian-image

#2 Hosting a website
docker build -t jeetu-nginx-image .
docker run --rm -it -p 8082:80 jeetu-nginx-image
"-it" is "-i" interactive and "-t" allocate a pseudo-TTY. This is to see the webserver logs in the same command window (press ^C to return back to powershell, and container stops and is deleted because of "--rm").

#3
#Sharing files from volume, between two containers
jdhall@Keysha-WindowsPC:/mnt/c/Users/jeete$ docker run --name=website5 -d -p 8085:80 -v /mnt/c/mydrive/git/ds/docker/educative-io/:/usr/share/nginx/html/ nginx:1.15
jdhall@Keysha-WindowsPC:/mnt/c/Users/jeete$ docker run --name=website6 -d -p 8086:80 -v /mnt/c/mydrive/git/ds/docker/educative-io/:/usr/share/nginx/html/ nginx:1.15
I see the same index.html loaded at both localhost:8085 and localhost:8086.


