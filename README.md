# django-with-custom-image

virtualenv -p python3 venv
source venv/bin/activate
pip install django
django-admin startproject dockerdjango

cd dockerdjango

python manage.py startapp blog

vi Dockerfile
vi start

vi dockerdjango/settings.py
vi dockerdjango/urls.py

mkdir -p blog/templates/blog
vi blog/templates/blog/index.html
vi blog/views.py

docker build -t dockerdjango .
docker run -d -p 8000:8000 --name dockerdjango dockerdjango:latest

docker login
docker tag dockerdjango:latest aan308/dockerdjango:latest
docker push aan308/dockerdjango:latest

docker run -d -p 8000:8000 --name dockerdjango aan308/dockerdjango:latest
