
# Steps to start django server


  install required packages:

      pip3 install -r requirements.txt

  make migrations for DB:

      python3.6 manage.py makemigrations

  apply the migrations:

      python3.6 manage.py migrate

  start the server:

      python3.6 manage.py runserver 0.0.0.0:8000
