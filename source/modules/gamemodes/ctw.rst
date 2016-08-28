Capture The Wool
================

Wools are a gamemode which objective is to capture other team(s) wool(s) in order to win the match. They are placed on
the victory monument(s). Victory monuments' regions are protected by default, to prevent it from being blocked with
another block.

================  ========================================
Elements          Description
================  ========================================
<wools> </wools>  Node containing all the wools on the XML
<wool>  </wool>   A victory monument's wool
================  ========================================

Wool attributes
---------------

+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| Attribute                    | Description.                                                              | Value            | Default value |
+==============================+===========================================================================+==================+===============+
| id                           | Unique identified used to reference the wool from other parts of the XML. | String           | REQUIRED      |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| color                        | The wool's color.                                                         | `Dye color`_     | REQUIRED      |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| team                         | The team which has to place the wool.                                     | `Team id`_       | REQUIRED      |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| location                     | Location of the woolroom, used to calculate proximity.                    | X,Y,Z            | REQUIRED      |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| monument                     | The wool monument - where you must place the wool.                        | Region_          | REQUIRED      |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| requierd                     | Whether the wool is required in order to win and end the match.           | Boolean          | True          |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| show                         | If false, the objective will be completely hidden.                        | Boolean          | True          |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| craftable                    | If set to false, the crafting of that wool is disabled.                   | Boolean          | False         |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| woolproximity-metric         | Metric used to calculate the wool's proximity [#f1]_ .                    | Proximity metric | Closest kill  |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| woolproximity-horizontal     | Disregard the Y axis when calculating the wool's proximity.               | Boolean          | False         |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| monumentproximity-metric     | Metric used to calculate the wool monument's proximity [#f1]_ .           | Proximity metric | Closest block |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+
| monumentproximity-horizontal | Disregard the Y axis when calculating the wool monument's proximity.      | Boolean          | False         |
+------------------------------+---------------------------------------------------------------------------+------------------+---------------+

.. _color: /reference/dye_colors
.. _id: /modules/main_map
.. _Region: /modules/regions
.. [#f1] Accepts closest player, closest block or closest kill.


Example:
--------

::

   <wools team="red">
       <wool color="cyan" location="-60.5,26,-118.5" monument="cyan-monument"/>
       <wool color="lime" location="-60.5,26,-121.5" monument="lime-monument"/>
   </wools>
   <wools team="blue">
       <wool color="magenta" location="-32.5,14,0.5" monument="magenta-monument"/>
       <wool color="pink" location="0.5,10,21.5" monument="pink-monument"/>
   </wools>


