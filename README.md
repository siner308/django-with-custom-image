# django-with-custom-image

virtualenv -p python3 venv
source venv/bin/activate
pip install django
django-admin startproject dockerdjango

cd dockerdjango

python manage.py startapp blog

vi Dockerfile
vi entrypoint.sh

vi dockerdjango/settings.py
vi dockerdjango/urls.py

mkdir -p blog/templates/blog
vi blog/templates/blog/index.html
vi blog/views.py

docker build -t dockerdjango .
docker run -d -p 8000:8000 --name my_docker_django dockerdjango:latest


// docker ps -a
// docker logs -f dockerdjdango
