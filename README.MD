# Profile REST API
ls ~/.ssh
ssh-keygen -t rsa -b 4096 -C "sijimonr@gmail.com"
# it generate id_rsa[private key]  id_rsa.pub [Public key]


# Vagrant setup

> vagrant init ubuntu/bionic64
> vagrant up --provider=vmware_desktop
> vagrent ssh
> vagrant destroy

> vagrant halt
> vagrant reload --provision

==========Python Virtual Environment===============

# Activate virtual env
source ~/env/bin/activate
# Deactivate Virtual env
dactivate


# and new version https://pypi.org/search?q=django
# ================= Install django and django rest framework=======
django==2.2
djangorestframework==3.9.2

pip install -r requirements.txt 


python -m venv ~/env


# Start project
django-admin.py startproject profiles_project .

python manage.py startapp profiles_api

# test using django development web server make it available on all network server adaptor

python manage.py runserver 0.0.0.0:8000

source ~/env/bin/activate
python manage.py makemigrations profiles_api