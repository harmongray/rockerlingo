# start with r-bspm rocker image:
FROM rocker/r-bspm:22.04

# add dependencies:
RUN apt-get update && apt-get install -y libcairo2-dev

# use four cores for builds:
ENV MAKE="make -j4"

# install packages:
RUN R -e "install.packages('udpipe', repos='http://cran.rstudio.com/')" \
    && R -e "install.packages('flextable', repos='http://cran.rstudio.com/')" \
    && R -e "install.packages('remotes', repos='http://cran.rstudio.com/')" \
    && R -e "remotes::install_github('rlesur/klippy')"

