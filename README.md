# django-with-custom-image

virtualenv -p python3 venv<br>
source venv/bin/activate<br>
pip install django<br>
django-admin startproject dockerdjango

cd dockerdjango

python manage.py startapp blog

vi Dockerfile<br>
vi start

vi dockerdjango/settings.py<br>
vi dockerdjango/urls.py

mkdir -p blog/templates/blog<br>
vi blog/templates/blog/index.html<br>
vi blog/views.py

docker build -t dockerdjango .<br>
docker run -d -p 8000:8000 --name dockerdjango dockerdjango:latest

docker login<br>
docker tag dockerdjango:latest aan308/dockerdjango:latest<br>
docker push aan308/dockerdjango:latest

docker run -d -p 8000:8000 --name dockerdjango aan308/dockerdjango:latest
