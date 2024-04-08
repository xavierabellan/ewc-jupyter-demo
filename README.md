# Setup a simple Jupyterhub on EWC with Ansible

This is an Ansible playbook and associated role to install a minimal functioning JupyterHub on an existing instance on the European Weather Cloud (EWC). 

It will install conda if not present, and create a conda environment with the Jupyter stack to run Jupyterhub as a system service.

The instance requires a public IP and DNS name, and will expose the JupyterHub through standard HTTPS, using a Let's encrypt certificate.

The playbook can be run standalone, defining your email address for the creation of the certificate:

    ansible-plabook -e cert_email=your.email@domain.org jupyter.yml

or integrated within your EWC Morpheus portal via Library - Integrations. In that case the email for the certificate will be taken from your own tenancy account.