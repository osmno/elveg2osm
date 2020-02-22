# elveg2osm

Conversion from Norwegian ELVEG road-data to OpenStreetMap

## ARCHIVED

This project is archived. See [nvdb2osm](https://github.com/NKAmapper/nvdb2osm) for the new import tool, which uses the API from Nasjonal Vegdatabase 


## Usage

**Note:** elveg2osm only works with `python2`, not with `python3`. You need to install the requirements with `pip2` and run the program with `python2` if both are installed.

1. [Install python2](https://www.python.org/downloads/release/python-2717/).

2. Install the required Python packages thusly:

```python
pip2 install -r requirements.txt
```

3. Get your data files from [Geonorge.no- ELVEG](https://kartkatalog.geonorge.no/metadata/ed1e6798-b3cf-48be-aee1-c0d3531da01a) or from [/geonorge/Samferdsel/Elveg/SOSI](https://nedlasting.geonorge.no/geonorge/Samferdsel/Elveg/SOSI) and unpack your files.

4. Unpack the `XXXXElveg.zip`, and put the unpacked files somewhere handy.

5. Run the program from the elveg2osm-folder thusly:

```python
python2 elveg2osm.py DIRECTORY MUNICIPALITY_NUMBER
```

Example:

```python
python2 elveg2osm.py 1201Elveg 1201
```

(Given your ELVEG-data is in the folder "1201Elveg", and that the municipalitynumber is 1201.)

6. After the program succeeds, the input-directory contains a file called XXXXElveg_default, which is the output of the command `sosi2osm XXXXElveg.SOS default.lua >XXXXElveg_default.osm`, and at least the file `XXXXFart.txt`.

XXXX is the 4-digit municipality number, listed for example at [wikipedia](https://no.wikipedia.org/wiki/Norges_kommuner#Kommunene).

## Requirements

- sosi2osm: For converting the initial SOSI file to OSM format (without changing the tags).
  - Our fork of the source code at [github.com/osmno/sosi2osm](https://github.com/osmno/sosi2osm).
  - Ubuntu PPA at [ppa.launchpad.net/saltmakrell/osm/ubuntu](http://ppa.launchpad.net/saltmakrell/osm/ubuntu/).
  - Available in Debian unstable.
- osmapis: Python module used for reading/writing/abstracting OSM-files.
  - Our fork of the source code at [github.com/osmno/osmapis](https://github.com/osmno/osmapis).
- geographiclib: Python module used for computing distances between nodes.
  - Homepage at [geographiclib.sourceforge.net](http://geographiclib.sourceforge.net/).
  - Source code at [pypi.python.org/pypi/geographiclib](https://pypi.python.org/pypi/geographiclib).
