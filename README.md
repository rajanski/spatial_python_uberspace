# Spatial Python on uberspace
How to get fiona, shapely and other spatial python packages running on uberspace

## Build & install the dependencies: geos, proj, gdal, spatialindex

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
./configure --prefix $HOME --with-geosconfig=$HOME/bin/geos-config
make && make install

wget http://download.osgeo.org/libspatialindex/spatialindex-src-1.7.0.tar.gz
tar xvzf spatialindex-src-1.7.0.tar.gz
cd spatialindex-src-1.7.0
./configure --prefix $HOME
make && make install

```



##Shapely, Fiona and pyproj

```python
pip2.7 install --user fiona  shapely pyproj rtree==0.7.0

```
##Set library paths

```bash
echo "export LD_LIBRARY_PATH=$HOME/lib/:$LD_LIBRARY_PATH" >> .bash_profile 
```
