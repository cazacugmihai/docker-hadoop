#!/usr/bin/env bash

IMAGE=cazacugmihai/hbase

build:
	docker build -t $(IMAGE) .
run:
	docker run -it --rm $(IMAGE)
shell:
	docker run -it --rm $(IMAGE) bash -c "start-hbase.sh; hbase shell"
bash:
	docker run -it --rm $(IMAGE) bash -c "start-hbase.sh; bash"