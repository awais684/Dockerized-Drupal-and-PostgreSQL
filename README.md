# Dockerized-Drupal-and-PostgreSQL
**Summary of Tasks:**

1. Create a virtual machine (EC2)
2. Install docker & docker-compose
3. Write a docker-compose file
4. Execute your file
5. Access your web server with VM public IP
6. Connect your application with the database
7. Watch my complete video of this project for troubleshooting
---

## Create a virtual machine (EC2)

I have already made a complete video on how to make a virtual machine, you can use this link to watch the video on my channel.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/i42CeeWTDDY/0.jpg)](https://www.youtube.com/watch?v=i42CeeWTDDY)

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
## 7. Watch my complete video of this project for troubleshooting 
I have already posted a video of this project on my channel If you face any issues and want to troubleshoot watch my complete video.

[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/FCpvi1X8jns/0.jpg)](https://www.youtube.com/watch?v=FCpvi1X8jns)





