# Installations steps

When the vagrant machine is up and launched, you need to finalize the installation by entering the following commands :

    sudo su postgres
    createuser -sPE vagrant

*If you want to have scripts for launching the odoo server*

    git clone https://github.com/babastienne/scripts_launch_odoo scripts 

*If you want to have the enterprise version of odoo*

    cd /odoo
    sudo git clone https://github.com/e-COSI/enterprise

## Launch Odoo

When you have launched odoo, you can access to the web view with the adress : 192.168.50.4:8069
