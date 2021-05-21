# Tryton Installation Guide for GNU Health
## System Requirements
  _The latest stable GNU Health Federation ecosystem uses these main resources:_
  * GNU_Health (gnuhealth-3.8.0)
  * Ubuntu 20.04 LTS
  * RDBMS Database: PostgreSQL >= 10.x
  * Python: >= 3.6 (Ubuntu 20.04 LTS has default python 3)
  * Gunicorn : 19.9
  * Flask : 1.0
  * Tryton 5.0
  * Bash shell
  * PIP for Python 3, verify through
  `` pip --version ``
  
  ## Installation Steps
  ### Step1 install dependencies
  _Execute commands in terminal_
  * ``sudo apt-get update``
  * ``sudo apt-get dist-upgrade``
  * ``apt-get install postgresql-server-dev-12 libxml2-dev libxslt-dev python3-dev pkg-config libfreetype6-dev postgresql patch python3-pip unoconv libpng-dev libjpeg8-dev``
  * Create a database user
  ``su - postgres -c "createuser --createdb --no-createrole --no-superuser gnuhealth"``
  
