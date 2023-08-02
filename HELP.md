app
To launch the application exec following command
    docker compose up -d 

backend
To compile our code using maven's docker, we use following command
    docker compose -f docker-compose-builder.yaml up backend_package
