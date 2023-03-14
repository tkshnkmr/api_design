# api_design


### Pre-requisite
1. Create python env
python3 -m venv ~/$YOUR_ENV_NAME
2. Activate
source ~/$YOUR_ENV_NAME/bin/activate
3. Install packages
python -m pip install -r requirements.txt



### Docker build
export IMAGE_NAME=api_demo

export TAG_VERSION=0.0.1

export CONTAINER_NAME=api_demo_container

docker build -t $IMAGE_NAME:$TAG_VERSION .

docker run -d --name $CONTAINER_NAME -p 80:80 $IMAGE_NAME:$TAG_VERSION


curl localhost:80

curl "localhost:80/items/123"

curl "localhost:80/items/345?q=query_param"

curl -X POST "localhost:80/items" -H 'Content-Type: application/json' -d '{"name":"my_name","price":123}' 
