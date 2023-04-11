Rendering and building the website using a reproducible docker container.

Geospatial data. 


```bash
docker run --rm -p 8787:8787 -e PASSWORD=YOURNEWPASSWORD -v /PATH/TO/WEBSITE/DIRECTORY:/home/rstudio/DATA rocker/geospatial
```

Browser:
http://localhost:8787/

user: rstudio
pass: YOURNEWPASSWORD 

Once signed in. Tools -> Global Options -> Appearance -> Editor theme: Solarized Dark 

install.packages("rinat")
install.packages("rgbif")
install.packages("data.table")
install.packages("maps")
install.packages("readxl")
install.packages("gpx")
install.packages("rayshader")
install.packages("rnaturalearth")
install.packages("rnaturalearthdata")

docker ps
docker commit -m "rocker_geospatial_website" 258aab99fd4b rocker_geospatial_website
docker image ls

Use the following for day to day website rendering

```bash
docker run --rm -p 8787:8787 -e PASSWORD=YOURNEWPASSWORD -v /PATH/TO/WEBSITE/DIRECTORY:/home/rstudio/DATA rocker_geospatial_website
```

Browser:
http://localhost:8787/

user: rstudio
pass: YOURNEWPASSWORD 