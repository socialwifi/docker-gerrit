# Gerrit Docker image
 Build a Docker image with the Gerrit code review system.
## Container Quickstart
1. Initialize and start gerrit.

 `$ docker run -d -p 8080:8080 -p 29418:29418 socialwifi/gerrit`

2. Open your browser to http://<dockerd host ip>:9000

## Use another container as the gerrit site storage.
1. Create a volume container.

 `$ docker run --name gerrit_volume socialwifi/gerrit echo "Gerrit volume container."`

2. Initialize and start gerrit using volume created above.

 `$ docker run -d --volumes-from gerrit_volume -p 8080:8080 -p 29418:29418 socialwifi/gerrit`

## Use local directory as the gerrit site storage.
1. Create a site directory for the gerrit site.

 `$ mkdir ~/gerrit_volume`

2. Initialize and start gerrit using the local directory created above.

 `$ docker run -d -v ~/gerrit_volume:/var/gerrit/review_site -p 8080:8080 -p 29418:29418 socialwifi/gerrit`

## Issues 
1. Timezone is UTC.
