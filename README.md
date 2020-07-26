## WebDAV Docker Project

This is my personal project with a intent to run a webdav server to access my folders from network. It uses docker and an ubuntu image with nginx configured. Needs docker-compose to build and run.

## Dependencies

To run this project you need docker and docker compose. Everything you need to install and configure is in the docs of official webpage:

[Docker](https://www.docker.com/get-started)

## Configuration

First copy the file env.example and rename it to ".env"; this file contains the envoironment variables used by the app. After that change the values of the .env file to suit your needs.

## How to run the app

Make sure you have docker and docker compose installed and configured. After that just run the command:

```
docker-compose up -d
```
Next, you can check if the container is up with the command:

```
docker ps
```

If everything is ok, you should see this result:

![Terminal](image.png?raw=true "Terminal")

In that example I used the port 19000 to give access to my folder.

## How to access the folders

Once you have configured the webdav server and you have the docker IP, you now can acces the content of the folders. The are a lot of file managers on many SOs (Linux, Android, iOS, etc) and browser extensions to do that, but normally in all those options you have to fill a form with the information of the IP address, user and password. In my example I can access the folder locally using the address 0.0.0.0:19000 or if the container is in another pc on the local network it can be accessed by PC_IP_ADDRESS:19000

## License

This project is licensed under the [MIT license](https://opensource.org/licenses/MIT).