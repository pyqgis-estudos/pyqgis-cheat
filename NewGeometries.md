

### CRIAÇÃO DE PONTO
[Fonte](https://howtoinqgis.wordpress.com/2016/10/23/how-to-create-a-memory-layer-from-the-python-console/)
```python
# Specify the geometry type
layer = QgsVectorLayer('Point?crs=epsg:4326', 'point' , 'memory')

# Set the provider to accept the data source
prov = layer.dataProvider()
point = QgsPointXY(100,100)

# Add a new feature and assign the geometry
feat = QgsFeature()
feat.setGeometry(QgsGeometry.fromPointXY(point))
prov.addFeatures([feat])

# Update extent of the layer
layer.updateExtents()

# Add the layer to the Layers panel
QgsProject.instance().addMapLayers([layer])
```
