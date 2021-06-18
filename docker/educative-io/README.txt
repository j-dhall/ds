Build a docker image using Dockerfile in the "." (current) directory
	docker build -f Dockerfile -t jeetu-debian-image .
Check that the image is created
	docker image ls
Create and run a container using the image. "--rm" will delete the created container after the run is completed
	docker run --rm jeetu-debian-image

