# Spatial Python on uberspace
How to get fiona, shapely and other spatial python packages running on uberspace

## geos, proj, gdal

```bash
#!/bin/bash
wget http://download.osgeo.org/geos/geos-3.5.0.tar.bz2
tar xvjf geos-3.5.0.tar.bz2
cd geos-3.5.0
./configure --prefix $HOME
make && make install
cd ..
wget http://download.osgeo.org/proj/proj-4.8.0.tar.gz
tar xvzf proj-4.8.0.tar.gz
cd proj-4.8.0
./configure --prefix $HOME
make && make install
cd ..

wget http://download.osgeo.org/gdal/1.11.1/gdal-1.11.1.tar.gz
tar xvzf gdal-1.11.1.tar.gz
cd gdal-1.11.1
./configure --prefix $HOME --with-geosconfig=$HOME/bin/geos-config --with-pg=/p$
make && make install

```

##Shapely, Fiona and pyproj

```python
easy_install-2.7 shapely #ä Doesnt work with pip for permission reasons
pip2.7 install fiona pyproj

```
