# Running

# On the registry machine run:
## Create the *volmue* directory:
	mkdir volume
## Run docker-compose
	docker-compose -f docker-compose.yaml up

# On the other machines:
## Edit the "/etc/hosts" file and add:
	<ip_of_registry_machine>      <name_of_the_registry>

#### Ex.: 
	1.2.3.4      local-image-registry

## Stop the docker daemon:
	service docker stop

## Edit the "/etc/docker/daemon.json" and add the line:
	"insecure-registries": ["<name_of_the_registry>:port"]

## Restart the docker daemon:
	service docker start