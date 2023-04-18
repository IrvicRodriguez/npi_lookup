# NPI Lookup

This project retrieves and stores information about healthcare providers using their National Provider Identifier (NPI) 
from the [NPPES NPI Registry](https://npiregistry.cms.hhs.gov). The data is fetched using the NPPES API and stored in an SQLite database.

## Installation

1. Clone this repository:

https://github.com/IrvicRodriguez/npi_lookup.git

2. Create and activate a virtual environment (optional but recommended): 

python3 -m venv venv
source venv/bin/activate

3. Install the required Python packages:

pip install -r requirements.txt

## Usage

To fetch and store NPI data for a specific NPI, run the following command:

python npi_lookup.py `<NPI>`


Replace `<NPI>` with the NPI number you want to look up. The script will fetch the provider's data from the NPPES API and store it in an SQLite database named `npi_lookup.db`.

## Configuration

By default, the script uses an SQLite database named `npi_lookup.db`. If you want to change the database name, update the `DATABASE_NAME` variable in the `npi_lookup.py` script.

##project structure
`npi-lookup/
|-- alembic/
|   |-- versions/
|   |   |-- <migration_files>.py
|   |-- env.py
|   |-- README
|   |-- script.py.mako
|-- models/
|   |-- __init__.py
|   |-- base.py
|   |-- npi.py
|   |-- address.py
|   |-- taxonomy.py
|-- tests/
|   |-- __init__.py
|   |-- test_npi_lookup.py
|-- .gitignore
|-- alembic.ini
|-- npi_lookup.py
|-- README.md
|-- requirements.txt`

## To run unittest: 

run: python tests/test_npi_lookup.py

`Expected output should be:  python tests/test_npi_lookup.py

.Error: NPI 0000000000 not found
..
----------------------------------------------------------------------
Ran 3 tests in 0.532s

OK
`