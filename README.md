# Dockerized-Drupal-and-PostgreSQL
**Summary of Tasks:**

1. Create a virtual machine (EC2)
2. Install docker & docker-compose
3. Write a docker-compose file
4. Execute your file
5. Access your web server with VM public IP
6. Connect your application with the database

---

## Create a virtual machine (EC2)

I have already made a complete video on how to make a virtual machine, you can use this link to watch the video on my channel.

<iframe width="560" height="315" src="https://www.youtube.com/embed/i42CeeWTDDY?si=uo4UnptEvoEcFBif" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---

## 2. Install docker & docker-compose


```
yum install docker -y
curl -SL https://github.com/docker/compose/releases/download/v2.20.3/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose;
```

---

## 3. Write a docker-compose file

```
version: '3.1'

services:
  drupal:
    container_name: drupal
    image: drupal
    ports:
      - "80:80"
    volumes:
      - drupal_modules:/var/www/html/modules
      - drupal_profiles:/var/www/html/profiles
      - drupal_themes:/var/www/html/themes
      - drupal_sites:/var/www/html/sites
    networks:
      - drupal_net

  postgres:
    container_name: psql
    image: postgres
    environment:
      POSTGRES_PASSWORD: awais123
    volumes:
      - psql_data:/var/lib/postgresql/data
    networks:
      - drupal_net

volumes:
  drupal_modules:
  drupal_profiles:
  drupal_themes:
  drupal_sites:
  psql_data:

networks:
  drupal_net:
```

---

## 4. Execute your file

```
docker-compose run -d
```

---

## 5. Access your web server with VM public IP
Copy the public IP of your virtual machine and paste it into the web browser. you will see following interface, Choose English and select Choose Profile,

![you will see following interface, Choose English and select Choose Profile,](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/kl8qygd3691ug4b3ry8z.PNG)
Go to next section & choose standard

![choose Standard](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1iysggiui05gnpmrzy38.PNG)

## 6. Connect your application with the database

Configure your database
![Configure your database](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/is9k9hlucdutzjbaz8oe.PNG)

Here is your final Application
![Here is your final Application](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/63tputkmgkfspj0dvem6.PNG)

---
I have already posted a video of this project on my channel you can watch my video for complete details.
{% embed https://youtu.be/FCpvi1X8jns %}

