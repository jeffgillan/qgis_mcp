# PyQGIS Class Quick Reference

**Generated:** 2026-01-17 20:36:59

This reference provides import paths, constructors, common methods, and usage examples for PyQGIS classes.
It complements the task-focused documentation in `pygis_docs/` by providing a class-focused lookup reference.

## Table of Contents
- [Core Data Classes](#core-data-classes)
- [Layout & Rendering](#layout--rendering)
- [Styling & Symbology](#styling--symbology)
- [Qt GUI Classes](#qt-gui-classes)
- [Qt Core Classes](#qt-core-classes)
- [Frequently Missing Imports](#frequently-missing-imports)

---

## Core Data Classes

### QgsProject

**Import:** `from qgis.core import QgsProject`

**Purpose:** Encapsulates a QGIS project, including sets of map layers and their styles,

**Constructor:**
```python
QgsProject(*args, **kwargs)
```

**Common Methods:**
- `FileFormat(value, names=None, ...)` - Flags which control project read behavior.
- `ReadFlag(value, names=None, ...)` - Flags which control project read behavior.
- `ReadFlags(...)` - Qgis.ProjectReadFlags()
- `absoluteFilePath(...)` - absoluteFilePath(self) -> str
- `addMapLayer(...)` - addMapLayer(self, mapLayer: QgsMapLayer, addToLegend: bool = True) -> QgsMapLayer
- `addMapLayers(...)` - addMapLayers(self, mapLayers: Iterable[QgsMapLayer], addToLegend: bool = True) -> List[QgsMapLayer]
- `attachedFiles(...)` - attachedFiles(self) -> List[str]
- `avoidIntersectionsLayers(...)` - avoidIntersectionsLayers(self) -> List[QgsVectorLayer]
- `avoidIntersectionsLayersChanged(...)` - avoidIntersectionsLayersChanged(self)
- `backgroundColor(...)` - backgroundColor(self) -> QColor
- `backgroundColorChanged(...)` - backgroundColorChanged(self)
- `baseName(...)` - baseName(self) -> str

**Example:**
```python
project = QgsProject.instance()
project.addMapLayer(layer)
project.write()
```

---

### QgsVectorLayer

**Import:** `from qgis.core import QgsVectorLayer`

**Purpose:** Represents a vector layer which manages a vector based data sets.

**Constructor:**
```python
QgsVectorLayer(*args, **kwargs)
```

**Common Methods:**
- `FeatureAvailability(value, names=None, ...)` - Possible return value for :py:func:`QgsFeatureSource.hasFeatures()` to determine if a source is empt
- `LayerFlag(...)` - int([x]) -> integer
- `LayerFlags(...)` - QgsMapLayer.LayerFlags()
- `LayerOptions(...)` - Setting options for loading vector layers.
- `LayerType(value, names=None, ...)` - Types of layers that can be added to a map
- `ReadFlag(...)` - int([x]) -> integer
- `ReadFlags(...)` - QgsMapLayer.ReadFlags()
- `addAttribute(...)` - addAttribute(self, field: QgsField) -> bool
- `addCurvedPart(...)` - addCurvedPart(self, ring: QgsCurve) -> Qgis.GeometryOperationResult
- `addCurvedRing(...)` - addCurvedRing(self, ring: QgsCurve) -> Tuple[Qgis.GeometryOperationResult, int]
- `addExpressionField(...)` - addExpressionField(self, exp: str, fld: QgsField) -> int
- `addFeature(...)` - addFeature(self, feature: QgsFeature, flags: Union[QgsFeatureSink.Flags, QgsFeatureSink.Flag] = QgsF

**Example:**
```python
layer = QgsVectorLayer("/path/to/file.shp", "My Layer", "ogr")
if layer.isValid():
    print(f"Features: {layer.featureCount()}")
```

---

### QgsRasterLayer

**Import:** `from qgis.core import QgsRasterLayer`

**Purpose:** Represents a raster layer.

**Constructor:**
```python
QgsRasterLayer(*args, **kwargs)
```

**Common Methods:**
- `LayerFlag(...)` - int([x]) -> integer
- `LayerFlags(...)` - QgsMapLayer.LayerFlags()
- `LayerOptions(...)` - Setting options for loading raster layers.
- `LayerType(value, names=None, ...)` - Raster layer types.
- `ReadFlag(...)` - int([x]) -> integer
- `ReadFlags(...)` - QgsMapLayer.ReadFlags()
- `attributeTableCount(...)` - attributeTableCount(self) -> int
- `bandCount(...)` - bandCount(self) -> int
- `bandName(...)` - bandName(self, bandNoInt: int) -> str
- `canCreateRasterAttributeTable(...)` - canCreateRasterAttributeTable(self) -> bool
- `createMapRenderer(...)` - createMapRenderer(self, rendererContext: QgsRenderContext) -> QgsMapLayerRenderer
- `createProfileGenerator(...)` - createProfileGenerator(self, request: QgsProfileRequest) -> QgsAbstractProfileGenerator

**Example:**
```python
layer = QgsRasterLayer("/path/to/raster.tif", "My Layer", "gdal")
if layer.isValid():
    print(f"Bands: {layer.bandCount()}")
```

---

### QgsFeature

**Import:** `from qgis.core import QgsFeature`

**Purpose:** The feature class encapsulates a single feature including its unique ID,

**Constructor:**
```python
QgsFeature(*args, **kwargs)
```

**Common Methods:**
- `attributeCount(...)` - attributeCount(self) -> int
- `attributeMap(...)` - attributeMap(self) -> Dict[str, Optional[object]]
- `fieldNameIndex(...)` - fieldNameIndex(self, fieldName: str) -> int
- `isUnsetValue(...)` - isUnsetValue(self, fieldIdx: int) -> bool
- `isValid(...)` - isValid(self) -> bool
- `resizeAttributes(...)` - resizeAttributes(self, fieldCount: int)
- `setAttribute(...)` - setAttribute(self, field: int, attr: Optional[Union[bool, int, float, str, Any]]) -> bool
- `setAttributes(...)` - setAttributes(self, attrs: object)
- `setEmbeddedSymbol(...)` - setEmbeddedSymbol(self, symbol: QgsSymbol)
- `setFields(...)` - setFields(self, fields: QgsFields, initAttributes: bool = True)
- `setGeometry(...)` - setGeometry(self, geometry: QgsGeometry)
- `setId(...)` - setId(self, id: int)

---

### QgsGeometry

**Import:** `from qgis.core import QgsGeometry`

**Purpose:** A geometry is the spatial representation of a feature.

**Constructor:**
```python
QgsGeometry(*args, **kwargs)
```

**Common Methods:**
- `ValidationMethod(value, names=None, ...)` - Available engines for validating geometries.
- `ValidityFlag(value, names=None, ...)` - Geometry validity check flags.
- `ValidityFlags(...)` - Qgis.GeometryValidityFlags()
- `addPart(...)` - addPart(self, part: QgsAbstractGeometry, geomType: Qgis.GeometryType = Qgis.GeometryType.Unknown) ->
- `addPartGeometry(...)` - addPartGeometry(self, newPart: QgsGeometry) -> Qgis.GeometryOperationResult
- `addPartV2(...)` - addPartV2(self, part: QgsAbstractGeometry, wkbType: Qgis.WkbType = Qgis.WkbType.Unknown) -> Qgis.Geo
- `addPoints(...)` - addPoints(self, points: Iterable[QgsPoint], geomType: Qgis.GeometryType = Qgis.GeometryType.Unknown)
- `addPointsV2(...)` - addPointsV2(self, points: Iterable[QgsPoint], wkbType: Qgis.WkbType = Qgis.WkbType.Unknown) -> Qgis.
- `addPointsXY(...)` - addPointsXY(self, points: Iterable[QgsPointXY], geomType: Qgis.GeometryType = Qgis.GeometryType.Unkn
- `addPointsXYV2(...)` - addPointsXYV2(self, points: Iterable[QgsPointXY], wkbType: Qgis.WkbType = Qgis.WkbType.Unknown) -> Q
- `addRing(...)` - addRing(self, ring: Iterable[QgsPointXY]) -> Qgis.GeometryOperationResult
- `addTopologicalPoint(...)` - addTopologicalPoint(self, point: QgsPoint, snappingTolerance: float = 1e-08, segmentSearchEpsilon: f

---

### QgsField

**Import:** `from qgis.core import QgsField`

**Purpose:** Encapsulate a field in an attribute table or data source.

**Constructor:**
```python
QgsField(*args, **kwargs)
```

**Common Methods:**
- `displayName(...)` - displayName(self) -> str
- `displayNameWithAlias(...)` - displayNameWithAlias(self) -> str
- `editorWidgetSetup(...)` - editorWidgetSetup(self) -> QgsEditorWidgetSetup
- `isReadOnly(...)` - isReadOnly(self) -> bool
- `name(...)` - name(self) -> str
- `readableConfigurationFlag(...)` - readableConfigurationFlag(flag: Qgis.FieldConfigurationFlag) -> str
- `setAlias(...)` - setAlias(self, alias: str)
- `setComment(...)` - setComment(self, comment: str)
- `setConfigurationFlags(...)` - setConfigurationFlags(self, flags: Union[Qgis.FieldConfigurationFlags, Qgis.FieldConfigurationFlag])
- `setConstraints(...)` - setConstraints(self, constraints: QgsFieldConstraints)
- `setDefaultValueDefinition(...)` - setDefaultValueDefinition(self, defaultValueDefinition: QgsDefaultValue)
- `setDuplicatePolicy(...)` - setDuplicatePolicy(self, policy: Qgis.FieldDuplicatePolicy)

---

### QgsFields

**Import:** `from qgis.core import QgsFields`

**Purpose:** Container of fields for a vector layer.

**Constructor:**
```python
QgsFields(*args, **kwargs)
```

**Common Methods:**
- `count(...)` - count(self) -> int
- `indexFromName(...)` - indexFromName(self, fieldName: str) -> int
- `names(...)` - names(self) -> List[str]
- `remove(...)` - remove(self, fieldIdx: int)
- `rename(...)` - rename(self, fieldIdx: int, name: str) -> bool
- `size(...)` - size(self) -> int

---

### QgsCoordinateReferenceSystem

**Import:** `from qgis.core import QgsCoordinateReferenceSystem`

**Purpose:** This class represents a coordinate reference system (CRS).

**Constructor:**
```python
QgsCoordinateReferenceSystem(*args, **kwargs)
```

**Common Methods:**
- `CrsType(...)` - int([x]) -> integer
- `celestialBodyName(...)` - celestialBodyName(self) -> str
- `createCompoundCrs(...)` - createCompoundCrs(horizontalCrs: QgsCoordinateReferenceSystem, verticalCrs: QgsCoordinateReferenceSy
- `createFromId(...)` - createFromId(self, id: int, type: QgsCoordinateReferenceSystem.CrsType = QgsCoordinateReferenceSyste
- `createFromOgcWmsCrs(...)` - createFromOgcWmsCrs(self, crs: str) -> bool
- `createFromProj(...)` - createFromProj(self, projString: str) -> bool
- `createFromProj4(...)` - createFromProj4(self, projString: str) -> bool
- `createFromSrid(...)` - createFromSrid(self, srid: int) -> bool
- `createFromSrsId(...)` - createFromSrsId(self, srsId: int) -> bool
- `createFromString(...)` - createFromString(self, definition: str) -> bool
- `createFromUserInput(...)` - createFromUserInput(self, definition: str) -> bool
- `createFromWkt(...)` - createFromWkt(self, wkt: str) -> bool

---

### QgsExpression

**Import:** `from qgis.core import QgsExpression`

**Purpose:** Class for parsing and evaluation of expressions (formerly called "search strings").

**Constructor:**
```python
QgsExpression(*args, **kwargs)
```

**Common Methods:**
- `addVariableHelpText(...)` - addVariableHelpText(name: str, description: str) -> bool
- `createFieldEqualityExpression(...)` - createFieldEqualityExpression(fieldName: str, value: Any, fieldType: QMetaType.Type = QMetaType.Type
- `expressionToLayerFieldIndex(...)` - expressionToLayerFieldIndex(expression: str, layer: QgsVectorLayer) -> int
- `functionCount(...)` - functionCount() -> int
- `isFunctionName(...)` - isFunctionName(name: str) -> bool
- `isValid(...)` - isValid(self) -> bool
- `setAreaUnits(...)` - setAreaUnits(self, unit: Qgis.AreaUnit)
- `setDistanceUnits(...)` - setDistanceUnits(self, unit: Qgis.DistanceUnit)
- `setEvalErrorString(...)` - setEvalErrorString(self, str: str)
- `setExpression(...)` - setExpression(self, expression: str)
- `setGeomCalculator(...)` - setGeomCalculator(self, calc: QgsDistanceArea)

---

### QgsFeatureRequest

**Import:** `from qgis.core import QgsFeatureRequest`

**Purpose:** This class wraps a request for features to a vector layer (or directly its vector data provider).

**Constructor:**
```python
QgsFeatureRequest(*args, **kwargs)
```

**Common Methods:**
- `InvalidGeometryCheck(value, names=None, ...)` - Methods for handling of features with invalid geometries
- `acceptFeature(...)` - acceptFeature(self, feature: QgsFeature) -> bool
- `addOrderBy(...)` - addOrderBy(self, expression: str, ascending: bool = True) -> QgsFeatureRequest
- `destinationCrs(...)` - destinationCrs(self) -> QgsCoordinateReferenceSystem
- `filterRect(...)` - filterRect(self) -> QgsRectangle
- `invalidGeometryCheck(...)` - invalidGeometryCheck(self) -> Qgis.InvalidGeometryCheck
- `setConnectionTimeout(...)` - setConnectionTimeout(self, connectionTimeout: int) -> QgsFeatureRequest
- `setCoordinateTransform(...)` - setCoordinateTransform(self, transform: QgsCoordinateTransform) -> QgsFeatureRequest
- `setDestinationCrs(...)` - setDestinationCrs(self, crs: QgsCoordinateReferenceSystem, context: QgsCoordinateTransformContext) -
- `setDistanceWithin(...)` - setDistanceWithin(self, geometry: QgsGeometry, distance: float) -> QgsFeatureRequest
- `setExpressionContext(...)` - setExpressionContext(self, context: QgsExpressionContext) -> QgsFeatureRequest
- `setFeedback(...)` - setFeedback(self, feedback: QgsFeedback)

---

### QgsRectangle

**Import:** `from qgis.core import QgsRectangle`

**Purpose:** A rectangle specified with double values.

**Constructor:**
```python
QgsRectangle(*args, **kwargs)
```

**Common Methods:**
- `center(...)` - center(self) -> QgsPointXY
- `combineExtentWith(...)` - combineExtentWith(self, rect: QgsRectangle)
- `fromCenterAndSize(...)` - fromCenterAndSize(center: QgsPointXY, width: float, height: float) -> QgsRectangle
- `height(...)` - height(self) -> float
- `set(...)` - set(self, p1: QgsPointXY, p2: QgsPointXY, normalize: bool = True)
- `setMinimal(...)` - setMinimal(self)
- `setNull(...)` - setNull(self)
- `setXMaximum(...)` - setXMaximum(self, x: float)
- `setXMinimum(...)` - setXMinimum(self, x: float)
- `setYMaximum(...)` - setYMaximum(self, y: float)
- `setYMinimum(...)` - setYMinimum(self, y: float)
- `toRectF(...)` - toRectF(self) -> QRectF

---

## Layout & Rendering

### QgsPrintLayout

**Import:** `from qgis.core import QgsPrintLayout`

**Purpose:** Print layout, a :py:class:`QgsLayout` subclass for static or atlas-based layouts.

**Constructor:**
```python
QgsPrintLayout(*args, **kwargs)
```

**Common Methods:**
- `SceneLayer(...)` - int([x]) -> integer
- `SceneLayers(...)` - QGraphicsScene.SceneLayers()
- `addEllipse(...)` - addEllipse(self, QRectF, pen: Union[QPen, QColor, Qt.GlobalColor, QGradient] = QPen(), brush: Union[
- `addItem(...)` - addItem(self, QGraphicsItem)
- `addItemsFromXml(...)` - addItemsFromXml(self, parentElement: QDomElement, document: QDomDocument, context: QgsReadWriteConte
- `addLayoutItem(...)` - addLayoutItem(self, item: QgsLayoutItem)
- `addLine(...)` - addLine(self, QLineF, pen: Union[QPen, QColor, Qt.GlobalColor, QGradient] = QPen()) -> QGraphicsLine
- `addMultiFrame(...)` - addMultiFrame(self, multiFrame: QgsLayoutMultiFrame)
- `addPath(...)` - addPath(self, QPainterPath, pen: Union[QPen, QColor, Qt.GlobalColor, QGradient] = QPen(), brush: Uni
- `addPixmap(...)` - addPixmap(self, QPixmap) -> QGraphicsPixmapItem
- `addPolygon(...)` - addPolygon(self, QPolygonF, pen: Union[QPen, QColor, Qt.GlobalColor, QGradient] = QPen(), brush: Uni
- `addRect(...)` - addRect(self, QRectF, pen: Union[QPen, QColor, Qt.GlobalColor, QGradient] = QPen(), brush: Union[QBr

**Example:**
```python
layout = QgsPrintLayout(project)
layout.initializeDefaults()
layout.setName("My Layout")
```

---

### QgsLayoutItemMap

**Import:** `from qgis.core import QgsLayoutItemMap`

**Purpose:** Layout graphical items for displaying a map.

**Constructor:**
```python
QgsLayoutItemMap(*args, **kwargs)
```

**Common Methods:**
- `ExportLayerBehavior(...)` - int([x]) -> integer
- `ExportLayerDetail(...)` - Contains details of a particular export layer relating to a layout item.
- `MapItemFlag(...)` - int([x]) -> integer
- `MapItemFlags(...)` - QgsLayoutItemMap.MapItemFlags()
- `ReferencePoint(...)` - int([x]) -> integer
- `addLabelBlockingItem(...)` - addLabelBlockingItem(self, item: QgsLayoutItem)
- `addRenderedFeatureHandler(...)` - addRenderedFeatureHandler(self, handler: QgsRenderedFeatureHandlerInterface)
- `adjustPointForReferencePosition(...)`
- `applyDataDefinedSize(...)`
- `applyItemSizeConstraint(...)`
- `atlasClippingSettings(...)` - atlasClippingSettings(self) -> QgsLayoutItemMapAtlasClippingSettings
- `attemptResize(...)` - attemptResize(self, size: QgsLayoutSize, includesFrame: bool = False)

**Example:**
```python
map_item = QgsLayoutItemMap(layout)
map_item.setRect(QRectF(0, 0, 200, 200))
map_item.zoomToExtent(layer.extent())
```

---

### QgsLayoutItemLabel

**Import:** `from qgis.core import QgsLayoutItemLabel`

**Purpose:** A layout item subclass for text labels.

**Constructor:**
```python
QgsLayoutItemLabel(*args, **kwargs)
```

**Common Methods:**
- `ExportLayerBehavior(...)` - int([x]) -> integer
- `ExportLayerDetail(...)` - Contains details of a particular export layer relating to a layout item.
- `ReferencePoint(...)` - int([x]) -> integer
- `adjustPointForReferencePosition(...)`
- `adjustSizeToText(...)` - adjustSizeToText(self)
- `applyDataDefinedSize(...)`
- `applyItemSizeConstraint(...)`
- `attemptResize(...)` - attemptResize(self, size: QgsLayoutSize, includesFrame: bool = False)
- `attemptSetSceneRect(...)` - attemptSetSceneRect(self, rect: QRectF, includesFrame: bool = False)
- `backgroundColor(...)` - backgroundColor(self, useDataDefined: bool = True) -> QColor
- `backgroundTaskCountChanged(...)` - backgroundTaskCountChanged(self, count: int)
- `boundingRect(...)` - boundingRect(self) -> QRectF

---

### QgsLayoutItemPage

**Import:** `from qgis.core import QgsLayoutItemPage`

**Purpose:** Item representing the paper in a layout.

**Constructor:**
```python
QgsLayoutItemPage(*args, **kwargs)
```

**Common Methods:**
- `ExportLayerBehavior(...)` - int([x]) -> integer
- `ExportLayerDetail(...)` - Contains details of a particular export layer relating to a layout item.
- `ReferencePoint(...)` - int([x]) -> integer
- `adjustPointForReferencePosition(...)`
- `applyDataDefinedSize(...)`
- `applyItemSizeConstraint(...)`
- `attemptResize(...)` - attemptResize(self, size: QgsLayoutSize, includesFrame: bool = False)
- `attemptSetSceneRect(...)` - attemptSetSceneRect(self, rect: QRectF, includesFrame: bool = False)
- `backgroundColor(...)` - backgroundColor(self, useDataDefined: bool = True) -> QColor
- `backgroundTaskCountChanged(...)` - backgroundTaskCountChanged(self, count: int)
- `boundingRect(...)` - boundingRect(self) -> QRectF
- `childrenBoundingRect(...)` - childrenBoundingRect(self) -> QRectF

---

### QgsLayoutPoint

**Import:** `from qgis.core import QgsLayoutPoint`

**Purpose:** This class provides a method of storing points, consisting of an x and y coordinate,

**Constructor:**
```python
QgsLayoutPoint(*args, **kwargs)
```

**Common Methods:**
- `decodePoint(...)` - decodePoint(string: str) -> QgsLayoutPoint
- `encodePoint(...)` - encodePoint(self) -> str
- `setPoint(...)` - setPoint(self, x: float, y: float)
- `setUnits(...)` - setUnits(self, units: Qgis.LayoutUnit)
- `setX(...)` - setX(self, x: float)
- `setY(...)` - setY(self, y: float)
- `toQPointF(...)` - toQPointF(self) -> QPointF

---

### QgsLayoutSize

**Import:** `from qgis.core import QgsLayoutSize`

**Purpose:** This class provides a method of storing sizes, consisting of a width and height,

**Constructor:**
```python
QgsLayoutSize(*args, **kwargs)
```

**Common Methods:**
- `decodeSize(...)` - decodeSize(string: str) -> QgsLayoutSize
- `encodeSize(...)` - encodeSize(self) -> str
- `height(...)` - height(self) -> float
- `setHeight(...)` - setHeight(self, height: float)
- `setSize(...)` - setSize(self, width: float, height: float)
- `setUnits(...)` - setUnits(self, units: Qgis.LayoutUnit)
- `setWidth(...)` - setWidth(self, width: float)
- `toQSizeF(...)` - toQSizeF(self) -> QSizeF
- `width(...)` - width(self) -> float

---

### QgsLayoutExporter

**Import:** `from qgis.core import QgsLayoutExporter`

**Purpose:** Handles rendering and exports of layouts to various formats.

**Constructor:**
```python
QgsLayoutExporter(*args, **kwargs)
```

**Common Methods:**
- `ExportResult(...)` - int([x]) -> integer
- `ImageExportSettings(...)` - Contains settings relating to exporting layouts to raster images
- `PageExportDetails(...)` - Contains details of a page being exported by the class
- `PdfExportSettings(...)` - Contains settings relating to exporting layouts to PDF
- `PrintExportSettings(...)` - Contains settings relating to printing layouts
- `SvgExportSettings(...)` - Contains settings relating to exporting layouts to SVG
- `computeWorldFileParameters(...)` - computeWorldFileParameters(self, dpi: float = -1) -> Tuple[float, float, float, float, float, float]
- `errorFile(...)` - errorFile(self) -> str
- `exportToImage(...)` - exportToImage(self, filePath: str, settings: QgsLayoutExporter.ImageExportSettings) -> QgsLayoutExpo
- `exportToPdf(...)` - exportToPdf(self, filePath: str, settings: QgsLayoutExporter.PdfExportSettings) -> QgsLayoutExporter
- `exportToPdfs(...)` - exportToPdfs(iterator: QgsAbstractLayoutIterator, baseFilePath: str, settings: QgsLayoutExporter.Pdf
- `exportToSvg(...)` - exportToSvg(self, filePath: str, settings: QgsLayoutExporter.SvgExportSettings) -> QgsLayoutExporter

**Example:**
```python
exporter = QgsLayoutExporter(layout)
exporter.exportToImage("output.png", QgsLayoutExporter.ImageExportSettings())
```

---

### QgsUnitTypes

**Import:** `from qgis.core import QgsUnitTypes`

**Purpose:** Helper functions for various unit types.

**Constructor:**
```python
QgsUnitTypes(*args, **kwargs)
```

**Common Methods:**
- `RenderUnit(value, names=None, ...)` - Rendering size units
- `decodeRenderUnit(...)` - decodeRenderUnit(string: str) -> Tuple[Qgis.RenderUnit, bool]

---

## Styling & Symbology

### QgsSingleBandGrayRenderer

**Import:** `from qgis.core import QgsSingleBandGrayRenderer`

**Purpose:** Raster renderer pipe for single band gray.

**Constructor:**
```python
QgsSingleBandGrayRenderer(*args, **kwargs)
```

**Common Methods:**
- `alphaBand(...)` - alphaBand(self) -> int
- `bandCount(...)` - bandCount(self) -> int
- `bandStatistics(...)` - bandStatistics(self, bandNo: int, stats: int, extent: QgsRectangle = QgsRectangle(), sampleSize: int
- `canCreateRasterAttributeTable(...)` - canCreateRasterAttributeTable(self) -> bool
- `colorInterpretationName(...)` - colorInterpretationName(self, bandNumber: int) -> str
- `create(...)` - create(elem: QDomElement, input: QgsRasterInterface) -> QgsRasterRenderer
- `createLegendNodes(...)` - createLegendNodes(self, nodeLayer: QgsLayerTreeLayer) -> List[QgsLayerTreeModelLegendNode]
- `dataTypeSize(...)` - dataTypeSize(self, bandNo: int) -> int
- `displayBandName(...)` - displayBandName(self, bandNumber: int) -> str
- `extent(...)` - extent(self) -> QgsRectangle
- `generateBandName(...)` - generateBandName(self, bandNumber: int) -> str
- `grayBand(...)` - grayBand(self) -> int

**Example:**
```python
renderer = QgsSingleBandGrayRenderer(layer.dataProvider(), 1)
layer.setRenderer(renderer)
layer.triggerRepaint()
```

---

### QgsSingleBandPseudoColorRenderer

**Import:** `from qgis.core import QgsSingleBandPseudoColorRenderer`

**Purpose:** Raster renderer pipe for single band pseudocolor.

**Constructor:**
```python
QgsSingleBandPseudoColorRenderer(*args, **kwargs)
```

**Common Methods:**
- `alphaBand(...)` - alphaBand(self) -> int
- `band(...)` - band(self) -> int
- `bandCount(...)` - bandCount(self) -> int
- `bandStatistics(...)` - bandStatistics(self, bandNo: int, stats: int, extent: QgsRectangle = QgsRectangle(), sampleSize: int
- `canCreateRasterAttributeTable(...)` - canCreateRasterAttributeTable(self) -> bool
- `colorInterpretationName(...)` - colorInterpretationName(self, bandNumber: int) -> str
- `create(...)` - create(elem: QDomElement, input: QgsRasterInterface) -> QgsRasterRenderer
- `createLegendNodes(...)` - createLegendNodes(self, nodeLayer: QgsLayerTreeLayer) -> List[QgsLayerTreeModelLegendNode]
- `createShader(...)` - createShader(self, colorRamp: QgsColorRamp = None, colorRampType: Qgis.ShaderInterpolationMethod = Q
- `dataTypeSize(...)` - dataTypeSize(self, bandNo: int) -> int
- `displayBandName(...)` - displayBandName(self, bandNumber: int) -> str
- `extent(...)` - extent(self) -> QgsRectangle

---

### QgsColorRampShader

**Import:** `from qgis.core import QgsColorRampShader`

**Purpose:** A ramp shader will color a raster pixel based on a list of values ranges in a ramp.

**Constructor:**
```python
QgsColorRampShader(*args, **kwargs)
```

**Common Methods:**
- `ColorRampItem(...)` - QgsColorRampShader.ColorRampItem()
- `classifyColorRamp(...)` - classifyColorRamp(self, classes: int = 0, band: int = -1, extent: QgsRectangle = QgsRectangle(), inp
- `classifyColorRampV2(...)` - classifyColorRampV2(self, band: int = -1, extent: QgsRectangle = QgsRectangle(), input: QgsRasterInt
- `colorRampItemList(...)` - colorRampItemList(self) -> List[QgsColorRampShader.ColorRampItem]
- `colorRampType(...)` - colorRampType(self) -> Qgis.ShaderInterpolationMethod
- `colorRampTypeAsQString(...)` - colorRampTypeAsQString(self) -> str
- `createColorRamp(...)` - createColorRamp(self) -> QgsColorRamp
- `legendSettings(...)` - legendSettings(self) -> QgsColorRampLegendNodeSettings
- `readXml(...)` - readXml(self, elem: QDomElement, context: QgsReadWriteContext = QgsReadWriteContext())
- `setClassificationMode(...)` - setClassificationMode(self, classificationMode: Qgis.ShaderClassificationMethod)
- `setClip(...)` - setClip(self, clip: bool)
- `setColorRampItemList(...)` - setColorRampItemList(self, list: Iterable[QgsColorRampShader.ColorRampItem])

---

### QgsRasterShader

**Import:** `from qgis.core import QgsRasterShader`

**Purpose:** Interface for all raster shaders.

**Constructor:**
```python
QgsRasterShader(*args, **kwargs)
```

**Common Methods:**
- `readXml(...)` - readXml(self, elem: QDomElement, context: QgsReadWriteContext = QgsReadWriteContext())
- `setMaximumValue(...)` - setMaximumValue(self, value: float)
- `setMinimumValue(...)` - setMinimumValue(self, value: float)
- `setRasterShaderFunction(...)` - setRasterShaderFunction(self, function: QgsRasterShaderFunction)
- `writeXml(...)` - writeXml(self, doc: QDomDocument, parent: QDomElement, context: QgsReadWriteContext = QgsReadWriteCo

---

### QgsRasterRenderer

**Import:** `from qgis.core import QgsRasterRenderer`

**Purpose:** Raster renderer pipe that applies colors to a raster.

**Constructor:**
```python
QgsRasterRenderer(*args, **kwargs)
```

**Common Methods:**
- `alphaBand(...)` - alphaBand(self) -> int
- `bandCount(...)` - bandCount(self) -> int
- `bandStatistics(...)` - bandStatistics(self, bandNo: int, stats: int, extent: QgsRectangle = QgsRectangle(), sampleSize: int
- `canCreateRasterAttributeTable(...)` - canCreateRasterAttributeTable(self) -> bool
- `colorInterpretationName(...)` - colorInterpretationName(self, bandNumber: int) -> str
- `createLegendNodes(...)` - createLegendNodes(self, nodeLayer: QgsLayerTreeLayer) -> List[QgsLayerTreeModelLegendNode]
- `dataTypeSize(...)` - dataTypeSize(self, bandNo: int) -> int
- `displayBandName(...)` - displayBandName(self, bandNumber: int) -> str
- `extent(...)` - extent(self) -> QgsRectangle
- `generateBandName(...)` - generateBandName(self, bandNumber: int) -> str
- `inputBand(...)` - inputBand(self) -> int
- `nodataColor(...)` - nodataColor(self) -> QColor

---

## Qt GUI Classes

### QColor

**Import:** `from qgis.PyQt.QtGui import QColor`

**Purpose:** QColor(Qt.GlobalColor)

**Constructor:**
```python
QColor(*args, **kwargs)
```

**Common Methods:**
- `NameFormat(...)` - int([x]) -> integer
- `alpha(...)` - alpha(self) -> int
- `alphaF(...)` - alphaF(self) -> float
- `colorNames(...)` - colorNames() -> List[str]
- `getCmyk(...)` - getCmyk(self) -> Tuple[int, int, int, int, int]
- `getCmykF(...)` - getCmykF(self) -> Tuple[float, float, float, float, float]
- `getHsl(...)` - getHsl(self) -> Tuple[int, int, int, int]
- `getHslF(...)` - getHslF(self) -> Tuple[float, float, float, float]
- `getHsv(...)` - getHsv(self) -> Tuple[int, int, int, int]
- `getHsvF(...)` - getHsvF(self) -> Tuple[float, float, float, float]
- `getRgb(...)` - getRgb(self) -> Tuple[int, int, int, int]
- `getRgbF(...)` - getRgbF(self) -> Tuple[float, float, float, float]

**Example:**
```python
color = QColor(255, 0, 0)  # Red
color = QColor("#FF0000")  # From hex
color.setAlpha(128)  # 50% transparent
```

---

### QFont

**Import:** `from qgis.PyQt.QtGui import QFont`

**Purpose:** QFont()

**Constructor:**
```python
QFont(*args, **kwargs)
```

**Common Methods:**
- `bold(...)` - bold(self) -> bool
- `italic(...)` - italic(self) -> bool
- `lastResortFont(...)` - lastResortFont(self) -> str
- `pixelSize(...)` - pixelSize(self) -> int
- `pointSize(...)` - pointSize(self) -> int
- `pointSizeF(...)` - pointSizeF(self) -> float
- `rawName(...)` - rawName(self) -> str
- `removeSubstitutions(...)` - removeSubstitutions(str)
- `setBold(...)` - setBold(self, bool)
- `setCapitalization(...)` - setCapitalization(self, QFont.Capitalization)
- `setFamilies(...)` - setFamilies(self, Iterable[str])
- `setFamily(...)` - setFamily(self, str)

**Example:**
```python
font = QFont("Arial", 12)
font.setBold(True)
font.setItalic(True)
```

---

### QBrush

**Import:** `from qgis.PyQt.QtGui import QBrush`

**Purpose:** QBrush()

**Constructor:**
```python
QBrush(*args, **kwargs)
```

**Common Methods:**
- `color(...)` - color(self) -> QColor
- `setColor(...)` - setColor(self, Union[QColor, Qt.GlobalColor, QGradient])
- `setStyle(...)` - setStyle(self, Qt.BrushStyle)
- `setTexture(...)` - setTexture(self, QPixmap)
- `setTextureImage(...)` - setTextureImage(self, QImage)
- `setTransform(...)` - setTransform(self, QTransform)

---

### QPen

**Import:** `from qgis.PyQt.QtGui import QPen`

**Purpose:** QPen()

**Constructor:**
```python
QPen(*args, **kwargs)
```

**Common Methods:**
- `color(...)` - color(self) -> QColor
- `dashOffset(...)` - dashOffset(self) -> float
- `setBrush(...)` - setBrush(self, Union[QBrush, QColor, Qt.GlobalColor, QGradient])
- `setCapStyle(...)` - setCapStyle(self, Qt.PenCapStyle)
- `setColor(...)` - setColor(self, Union[QColor, Qt.GlobalColor, QGradient])
- `setCosmetic(...)` - setCosmetic(self, bool)
- `setDashOffset(...)` - setDashOffset(self, float)
- `setDashPattern(...)` - setDashPattern(self, Iterable[float])
- `setJoinStyle(...)` - setJoinStyle(self, Qt.PenJoinStyle)
- `setMiterLimit(...)` - setMiterLimit(self, float)
- `setStyle(...)` - setStyle(self, Qt.PenStyle)
- `setWidth(...)` - setWidth(self, int)

---

## Qt Core Classes

### QRectF

**Import:** `from qgis.PyQt.QtCore import QRectF`

**Purpose:** QRectF()

**Constructor:**
```python
QRectF(*args, **kwargs)
```

**Common Methods:**
- `center(...)` - center(self) -> QPointF
- `getCoords(...)` - getCoords(self) -> Tuple[float, float, float, float]
- `getRect(...)` - getRect(self) -> Tuple[float, float, float, float]
- `height(...)` - height(self) -> float
- `isValid(...)` - isValid(self) -> bool
- `marginsAdded(...)` - marginsAdded(self, QMarginsF) -> QRectF
- `marginsRemoved(...)` - marginsRemoved(self, QMarginsF) -> QRectF
- `moveCenter(...)` - moveCenter(self, Union[QPointF, QPoint])
- `setBottom(...)` - setBottom(self, float)
- `setBottomLeft(...)` - setBottomLeft(self, Union[QPointF, QPoint])
- `setBottomRight(...)` - setBottomRight(self, Union[QPointF, QPoint])
- `setCoords(...)` - setCoords(self, float, float, float, float)

**Example:**
```python
rect = QRectF(0, 0, 100, 50)  # x, y, width, height
center = rect.center()
```

---

### QSizeF

**Import:** `from qgis.PyQt.QtCore import QSizeF`

**Purpose:** QSizeF()

**Constructor:**
```python
QSizeF(*args, **kwargs)
```

**Common Methods:**
- `height(...)` - height(self) -> float
- `isValid(...)` - isValid(self) -> bool
- `setHeight(...)` - setHeight(self, float)
- `setWidth(...)` - setWidth(self, float)
- `toSize(...)` - toSize(self) -> QSize
- `width(...)` - width(self) -> float

**Example:**
```python
size = QSizeF(100, 50)  # width, height
```

---

### QPointF

**Import:** `from qgis.PyQt.QtCore import QPointF`

**Purpose:** QPointF()

**Constructor:**
```python
QPointF(*args, **kwargs)
```

**Common Methods:**
- `setX(...)` - setX(self, float)
- `setY(...)` - setY(self, float)
- `toPoint(...)` - toPoint(self) -> QPoint

**Example:**
```python
point = QPointF(10.5, 20.5)  # x, y coordinates
```

---

### QSize

**Import:** `from qgis.PyQt.QtCore import QSize`

**Purpose:** QSize()

**Constructor:**
```python
QSize(*args, **kwargs)
```

**Common Methods:**
- `height(...)` - height(self) -> int
- `isValid(...)` - isValid(self) -> bool
- `setHeight(...)` - setHeight(self, int)
- `setWidth(...)` - setWidth(self, int)
- `width(...)` - width(self) -> int

---

### QPoint

**Import:** `from qgis.PyQt.QtCore import QPoint`

**Purpose:** QPoint()

**Constructor:**
```python
QPoint(*args, **kwargs)
```

**Common Methods:**
- `setX(...)` - setX(self, int)
- `setY(...)` - setY(self, int)

---

## Frequently Missing Imports

Common import errors and their solutions:

### Qt GUI Classes
**Problem:** `NameError: name 'QColor' is not defined`

**Solution:**
```python
from qgis.PyQt.QtGui import QColor, QFont, QBrush, QPen
```

### Qt Core Classes
**Problem:** `NameError: name 'QRectF' is not defined`

**Solution:**
```python
from qgis.PyQt.QtCore import QRectF, QSizeF, QPointF, QSize, QPoint
```

### Layout Page Classes
**Problem:** `NameError: name 'QgsLayoutItemPage' is not defined`

**Solution:**
```python
from qgis.core import QgsLayoutItemPage
```

### Complete Import Template
For layout/rendering work, use this comprehensive import template:
```python
from qgis.core import (
    QgsProject, QgsRasterLayer, QgsVectorLayer,
    QgsPrintLayout, QgsLayoutItemMap, QgsLayoutItemLabel,
    QgsLayoutPoint, QgsLayoutSize, QgsLayoutItemPage,
    QgsUnitTypes, QgsLayoutExporter,
    QgsSingleBandGrayRenderer, QgsRasterShader
)
from qgis.PyQt.QtGui import QColor, QFont, QBrush, QPen
from qgis.PyQt.QtCore import QRectF, QSizeF, QPointF
```

---

**Summary:** 33 classes documented with 326 methods