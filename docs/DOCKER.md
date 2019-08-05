# Docker

To install rest_variantValidator via Docker, first ensure you have both docker and docker-compose installed. 
See their [documentation](https://docs.docker.com/compose/install/) for information.

Then, clone the repository and move into that directory.

```bash
$ git clone https://github.com/openvar/rest_variantValidator
cd rest_variantValidator/
``` 

## Launch
You can then launch the docker containers and run them using

```bash
docker-compose up
```

Note, the first time this is run it will download each of the databases including the pre-populated
validator database and could take up to 30 minutes depending on your connection. We do not recommend
running this in the background as you need to see the logs and therefore when the databases are
ready to be used.


# The following is in place for reference, it needs to be updated!

## Run
Once installed and running it is possible to run just the container containing VariantValidator, either to 
run the validator script

```bash
docker-compose run vv variant_validator.py
```

run python

```bash
docker-compose run vv python
```

or go into the container via bash

```bash
docker-compose run vv bash
```

Note, that each time one of these commands is run a new container is created. 
For more information on how to use docker-compose see their [documentation](https://docs.docker.com/compose/).

It is possible to access both the UTA and Validator databases outside of docker as they expose the
 default PostgreSQL and MySQL ports (5432 and 3306 respectively). In the current set-up it is not possible to 
 access the seqrepo database outside of docker.
 
Finally, it should be noted that the current UTA docker container is not up-to-date and only contains the 
2017-10-26 release. Therefore use caution when interpreting these results, and be advised the
 VariantValidator tests will fail. 
 
 