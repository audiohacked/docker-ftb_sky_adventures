# Feed-The-Beast Sky Adventures (Modded Minecraft Map 1.12) in Docker
To pull the image:
```
docker pull audiohacked/ftb_sky_adventures:stable
```

It's highly recommended run a named data volume:
```
docker volume create minecraft_ftb_sky_adventures_data
docker volume create minecraft_ftb_sky_adventures_backups
```

Then, run the server container:
```
docker run --detach --interactive --tty \
    --name ftb_sky_adventures \
    --volume minecraft_ftb_sky_adventures_data:/minecraft/world \
    --volume minecraft_ftb_sky_adventures_backups:/minecraft/backups \
    --publish 25565:25565 \
    --env EULA=TRUE \
    audiohacked/ftb_sky_adventures:stable
```
