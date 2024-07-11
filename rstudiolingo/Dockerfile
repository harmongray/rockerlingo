# start with r-bspm rocker image:
FROM rocker/rstudio:4.4.0

# add dependencies:
RUN apt-get update && apt-get install -y libcairo2-dev

# make shared directory
RUN mkdir -p /home/docker_share/

# use four cores for builds:
ENV MAKE="make -j4"

# install packages:
RUN R -e "install.packages('udpipe', repos='http://cran.rstudio.com/')" \
    && R -e "install.packages('flextable', repos='http://cran.rstudio.com/')" \
    && R -e "install.packages('remotes', repos='http://cran.rstudio.com/')" \
    && R -e "remotes::install_github('rlesur/klippy')"

