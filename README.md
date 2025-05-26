Python Flask app using a multi-stage Distroless Docker image

docker build -t distroless-flask-app .
docker run -d -p 8080:8080 distroless-flask-app
Now visit: http://localhost:8080
