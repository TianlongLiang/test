# Container image that runs your code
FROM alpine:3.10

# Copies your code file from your action repository to the filesystem path `/` of the container
COPY entrypoint.sh /entrypoint.sh

# Code file to execute when the docker container starts up (`entrypoint.sh`)
# You can choose any base Docker image and, therefore, any language for your action. 
# The following shell script example uses the who-to-greet input variable to print "Hello [who-to-greet]" in the log file.
ENTRYPOINT ["/entrypoint.sh"]