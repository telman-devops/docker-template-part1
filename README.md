# docker-template-part1
Examples without docker-compose: volume, network, multi-containers(mongo, express, reactjs)

---------------------
Run Node API Container
---------------------

docker run --name goals-backend \
  -e MONGODB_USERNAME=max \
  -e MONGODB_PASSWORD=secret \
  -v logs:/app/logs \
  -v /Users/maximilianschwarzmuller/development/teaching/udemy/docker-complete/backend:/app \
  -v /app/node_modules \
  --rm \
  -d \
  --network goals-net \
  -p 80:80 \
  goals-node

---------------------
Build React SPA Image
---------------------

docker build -t goals-react .

---------------------
Run React SPA Container
---------------------

docker run --name goals-frontend \
  -v /Users/maximilianschwarzmuller/development/teaching/udemy/docker-complete/frontend/src:/app/src \
  --rm \
  -d \
  -p 3000:3000 \
  -it \
  goals-react

---------------------
Stop all Containers
---------------------

docker stop mongodb goals-backend goals-frontend
