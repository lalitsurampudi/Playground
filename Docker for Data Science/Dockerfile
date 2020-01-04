FROM continuumio/miniconda3

# Meta-data
LABEL maintainer="Lalit Surampudi <lalit.surampudi@gmail.com"
LABEL description="Dev environment for machine learning and data science team \
                  with access to shared data in network drive."

# Set the working directory to /data
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY . /app

# Install the required libraries
RUN apt update && \
    conda install -y python==3.7.3 -y && \
    conda install jupyter -y && \
    conda install python==3.7.3 -y && \
    conda install pandas==0.24.2 -y && \
    conda install seaborn==0.9.0 -y && \
    conda install -c conda-forge jupyterlab -y && \
    conda clean -y --all

# Make port 8888 available to the world outside this container
EXPOSE 8888

#  Peristing data in a folder with in the container
#VOLUME /data

# Run jupyter when container launches
CMD ["jupyter","lab","--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]