hodgeproj4.js -- Convenience for proj4js Javascript reprojection library.   
Author:      Jesse Bounds :: rebounds.net
Requirements: proj4js.js (http://trac.osgeo.org/proj4js) and Proj4 projection definitions (http://spatialreference.org/ref/epsg/)

hodgeproj4 makes it easier to use the Proj4js JavaScript library to transform point coordinates from one 
coordinate system to another, including datum transformations by wrapping calls to the underlying library
in a convenient, self documenting interface

Using it is a layup:

Simply include the requisite scripts in your page header:
	<!-- proj4js script from osgeo.org/proj4js -->
	<script src="/javascripts/proj4js-combined.js"></script>
	<!-- the proj4 projection definition (for any non WGS84/EPSG:4236 projection - 
		 you can find these at http://spatialreference.org/ref/epsg/) -->
	<script src="/javascripts/defs/EPSG2249.js"></script>
	<!-- yours truly -->
	<script src="/javascripts/hodgeproj4.js">

	*** NOTE: You do NOT have to include a script for WGS84/EPSG:4236 - proj4js has that one baked in! ***

Now, go ahead, do a projection transformation!
 
	// In this example, we go from Massachusetts State Plane to WGS84
	transformation = HodgeProj4.transform(761254.49731, 2944252.55218).from('EPSG2249').to('WGS84');
	
	// You just transformed x,y inline, so now you can do stuff like:
	drawDotOnMap(transformation.x, transformation.y);
	
You are so smart, nice job!
