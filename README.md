# Simple Jupyterhub on EWC with Ansible automation and example notebooks
This repository contains what is required to install JupyterHub on the European Weather Cloud (EWC), as well as some demp notebooks to showcase how to retrieve, manipulate and plot data from ECMWF.

## Ansible Automation
Under `ansible` you will find the Ansible playbook and associated role to install install and configure a minimal JupyterHub on an existing instance EWC. 

It will install conda if not present, and create a conda environment with the Jupyter stack to run Jupyterhub as a system service.

The instance requires a public IP and DNS name, and will expose the JupyterHub through standard HTTPS, using a Let's encrypt certificate.

The playbook can be run standalone, defining your email address for the creation of the certificate:
    
    cd ansible
    ansible-playbook -e cert_email=your.email@domain.org jupyter.yml

or integrated within your EWC Morpheus portal via Library - Integrations. In that case the email for the certificate will be taken from your own tenancy account.

## Jupyter Notebooks
Under `notebooks` you will find some simple Jupyter notebooks to showcase how to retrieve, manipulate and plot data from ECMWF Data services.
