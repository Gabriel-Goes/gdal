.. _raster.rraster:

================================================================================
RRASTER -- R Raster
================================================================================

.. shortname:: RRASTER

.. versionadded:: 2.2

.. built_in_by_default::

This is a read-only reader for the datasets handled by the `R Raster
package <https://cran.r-project.org/web/packages/raster/index.html>`__.
Those datasets are made of a .grd file, which is a text header file, and
a .gri binary file containing the raster data itself. The .grd is the
file opened by GDAL. Starting with GDAL 2.3, the driver will read
ratvalues as RAT or color tables. Layer names will be assigned to GDAL
band description. The 'creator' and 'created' attributes of the
'[general]' section will be assigned to the GDAL 'CREATOR' and 'CREATED'
dataset metadata items.

Starting with GDAL 2.3, the driver has write capabilities. Color tables
or RAT will be written. The 'CREATOR' and 'CREATED' dataset metadata
items will be written as the 'creator' and 'created' attributes of the
'[general]' section. Band description will be written as the 'layername'
attribute of the '[description]' section.

|about-creation-options|
The following creation options are supported:

-  .. co:: INTERLEAVE
      :choices: BIP, BIL, BSQ
      :default: BIL

      Respectively band interleaved by pixel, band
      interleaved by line, band sequential.
      Starting with GDAL 3.5, when copying from a source dataset with multiple bands
      which advertises a INTERLEAVE metadata item, if the INTERLEAVE creation option
      is not specified, the source dataset INTERLEAVE will be automatically taken
      into account.

-  .. co:: PIXELTYPE
      :choices: SIGNEDBYTE

      To write Byte bands as signed byte instead of unsigned byte.
      Starting with GDAL 3.7, this option is deprecated and Int8 should rather
      be used.

Driver capabilities
-------------------

.. supports_createcopy::

.. supports_create::

.. supports_georeferencing::

.. supports_virtualio::

See Also
--------

-  Description of the `"rasterfile"
   format <https://rspatial.org/raster/pkg/appendix2.html>`__

