# Docket NodeJS

            # Create Dcoker image
            docker build -t node-app-image .

            # Run Container
            docker run -p 3000:3000 -d --name node-app node-app-image

            # View File Sytem 
            docker exec -it node-app bash
            printenv

            # Volume (Bind Mount) sync file system with docker container
            1) docker run -v /home/miguel/DevOps/Docker/Node-Docker:/app -p 3000:3000 -d --name node-app node-app-image

            2) docker run -v $(pwd):/app -p 3000:3000 -d --name node-app node-app-image

            -> Read Only

            3) docker run -v $(pwd):/app:ro -v /app/node_modules -p 3000:3000 -d --name node-app node-app-image

            4) docker image rm node-app -fv

            5) docker prune

            # ENV variables
            1) docker run -v $(pwd):/app:ro -v /app/node_modules --env PORT=4000 -p 3000:4000 -d --name node-app node-app-image

            2) docker run -v $(pwd):/app:ro -v /app/node_modules --env-file ./.env -p 3000:4000 -d --name node-app node-app-image