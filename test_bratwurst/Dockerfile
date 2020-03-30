FROM hdsu/bratwurst_tensorflow2

LABEL maintainer="Andres Quintero a.quintero@dkfz-heidelberg.de"


#RUN R -e "devtools::install_github('andquintero/bratwurst', ref='dev_hdsu') "
RUN R -e "devtools::install_github('hdsu-bioquant/bratwurst', ref='dev_hdsu_lite') "
    
RUN R -e "BiocManager::install('DESeq2', update = FALSE)"
RUN R -e "BiocManager::install('gage', update = FALSE)"
RUN R -e "install.packages('DT')"


RUN useradd -ms /bin/bash hdsu

COPY --chown=hdsu /test_bratwurst/data /home/hdsu/Corces_NMF/data
COPY --chown=hdsu /test_bratwurst/src /home/hdsu/Corces_NMF/src
COPY --chown=hdsu /test_bratwurst/db /home/hdsu/Corces_NMF/db

COPY --chown=hdsu /test_bratwurst/user-settings /home/hdsu/.rstudio/monitored/user-settings/user-settings
COPY --chown=hdsu /test_bratwurst/Rprofile /home/hdsu/.Rprofile
COPY /test_bratwurst/user-settings /home/rstudio/.rstudio/monitored/user-settings/user-settings
COPY /test_bratwurst/Rprofile /home/rstudio/.Rprofile

# COPY --chown=hdsu data /home/hdsu/Corces_NMF/data
# COPY --chown=hdsu src /home/hdsu/Corces_NMF/src
# COPY --chown=hdsu db /home/hdsu/Corces_NMF/db
# COPY --chown=hdsu user-settings /home/hdsu/.rstudio/monitored/user-settings/user-settings
# COPY --chown=hdsu .Rprofile /home/hdsu/.Rprofile
# COPY .Rprofile /home/rstudio/.Rprofile
# COPY user-settings /home/rstudio/.rstudio/monitored/user-settings/user-settings


