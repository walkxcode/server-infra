<h1 align="center">
  📂 File Structure
</h1>

```graphql
# Data Root
/data/*
  ├─ data/docker - # Docker Data
  │  └─ docker/container - # Folders depending on container name
  │     ├─ container/data - # Container data
  │     ├─ container/config - # Container configuration files
  │     └─ container/docker-compose.yml # When deployed using docker compose
  └─ data/nas - # Mounted NAS drive
     └─ nas/media - # Media like movies & music
        ├─ media/movies - # Movies
        │  └─ movies/movie - # Folders depending on the movie name
        └─ media/music - # Music
           └─ music/artist - Folders depending on the artist name
              └─ arist/album - Folders depending on the album name
                 └─ album/song - Folders depending on the song name
```
