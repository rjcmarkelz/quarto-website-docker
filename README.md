Rendering and building the website using a reproducible docker container.

Geospatial data package as base (for my workflows).

Change the path to your website directory.

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

Save the *running* container to save all of your installed packages based on container ID (e.g. 258aab99fd4b) with the name "rocker_geospatial_website" as the name.

```bash
docker ps
docker commit -m "rocker_geospatial_website" 258aab99fd4b rocker_geospatial_website
docker image ls
```

Use the following for day to day website rendering using the name of the saved container.

```bash
docker run --rm -p 8787:8787 -e PASSWORD=YOURNEWPASSWORD -v /PATH/TO/WEBSITE/DIRECTORY:/home/rstudio/DATA rocker_geospatial_website
```

Browser:
http://localhost:8787/

user: rstudio
pass: YOURNEWPASSWORD 