# elveg2osm

Conversion from Elveg road-data to OpenStreetMap

## Usage

Get your data files from [Geonorge.no- ELVEG](https://kartkatalog.geonorge.no/metadata/ed1e6798-b3cf-48be-aee1-c0d3531da01a) and unpack your files

Install the required python packages with `pip install -r requirements.txt`

Run the program with `elveg2osm.py dir XXXX`

The directory dir contains a file called XXXXElveg\_default, which is the
output of the command
`sosi2osm XXXXElveg.SOS default.lua >XXXXElveg_default.osm`.
and at least the file `XXXXFart.txt`.

XXXX is the 4-digit municipality number, listed for example at [wikipedia](https://no.wikipedia.org/wiki/Norges_kommuner#Kommunene)

## Requirements

- sosi2osm:      For converting the initial SOSI file to OSM-format (without changing the tags)
   - Source code at https://github.com/Gnonthgol/sosi2osm
   - Ubuntu PPA at http://ppa.launchpad.net/saltmakrell/osm/ubuntu/
   - Available in Debian unstable
- osmapis:       Python module used for reading/writing/abstracting OSM-files
   - Source code at https://github.com/xificurk/osmapis
- geographiclib: Python module used for computing distances between nodes
   - Home page at http://geographiclib.sourceforge.net/
   - Source code at https://pypi.python.org/pypi/geographiclib
