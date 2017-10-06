#!/usr/bin/env bash

IMAGE=cazacugmihai/hadoop

build:
	docker build -t $(IMAGE) .
run:
	docker run -it --rm $(IMAGE)
bash:
	docker run -it --rm $(IMAGE) bash -c "/usr/sbin/sshd; bash"