FROM python:3.9

# Install pip, then use pip to install necessary Python packages
RUN pip install --no-cache-dir \
    numpy \
    pandas \
    matplotlib \
    jupyterlab \
    rocrate \
    rdflib \
    pyshacl

# Install DVC
RUN pip install dvc

# Install Quarto CLI
RUN curl -s https://install.quarto.org | bash
