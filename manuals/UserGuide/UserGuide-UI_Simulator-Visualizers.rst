.. VISUALIZERS COLUMN


Simple Visualizers
..................

Brain Activity Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~

A 3D scene of the brain activity:


- at the region level: the brain is represented by a coarse granularity - each 
  region is represented with only one color.

.. figure:: screenshots/visualizer_brain.jpg
   :width: 90%
   :align: center

   Preview for Brain Activity Visualizer at the region level

- at the surface level: the brain is represented by a fine granularity - each 
  surface vertex has an individual measure.



Time Series Visualizer (svg/d3)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: screenshots/visualizer_timeseries_svgd3.jpg
   :width: 90%
   :align: center

   Preview for Time-Series Visualizer (svg/d3)


Time Series Volume Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: screenshots/time_series_volume_visualizer.jpg
   :width: 90%
   :align: center

This visualizer displays time series of volumetric data, like fMRI.
There are three navigation quadrants on the left and one main "focus quadrant". 
It is also possible to navigate in space using the slide controls on the
top-left toolbar.

The playback function is activated by clicking the play button, while the time
series data is buffered from the server according to the currently selected
view.

A different color map can be selected by clicked the Brain button in the
top-right of the screen.

Time Series Fragment
~~~~~~~~~~~~~~~~~~~~

.. figure:: screenshots/time_series_fragment.jpg
   :width: 90%
   :align: center

This is an alternative time series visualizer written using D3.js.

It displays time series information about the selected nodes. If it is coupled
with the Time Series Volume Visualizer it displays signal values in time for
each selected voxel.
This visualizer is composed of three main parts:

*Global Time Series Graph:*
All previously selected lines are shown here. Some transparency is applied to
the lines and only one line is highlighted each time. Highlighting can be done
be passing the mouse over the line on the global graph or by clicking the
selected line in the sortable graph. Vertical scaling is done based only on the
selected values and not on the complete data set. A red vertical line shows the
current time point. A blue line follows the mouse showing the value of the
highlighted line at each point.

*Brush section:*
The brush function is used to display only a portion of the
data, zooming on it if possible. The user can manually select the brushing
extent while it will automatically set itself around the current time point
with a default extent during playback.

*Sortable Graph:*
Every selected time series is shown on each line and labeled
based on its coordinates. The lines are colored following the selected feature
in "Color Lines by" at the top of the screen. They are then sorted automatically
by one of the selected methods or manually, by dragging and dropping each line
in the desired position, as seen on the above picture. Lines can be removed by
dragging them to the top "trash bin area" that appear every time a line is
dragged.


Animated Time Series Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: screenshots/visualizer_timeseries_animated.jpg
   :width: 90%
   :align: center

   Preview for Animated Time Series Visualizer


This is an alternative of TVB for displaying signal lines in a 2D display.

The label "animated" comes from the red line which will pass the entire signal step by step, at a configurable
speed. In single mode, this red-line might not be very useful, but it makes more sense when the same 2D display
gets reused in the Dual Visualizers (combined with the 3D display on a surface) where the red-line shows the
current step displayed in the 3D movie on the left.

.. figure:: screenshots/visualizer_timeseries_channel_selection.jpg
   :width: 90%
   :align: center

   Selecting the "channels" to be displayed (available in several viewers of TVB).
   
   
Dual Brain Activity Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This visualizer combines the brain activity movie shown in a 3D display on the left,
with the explicit channels recording lines on the right.
Movie start/stop, speed control, color schema change, channel selection are some of the features available in this visualizer.


.. figure:: screenshots/visualizer_dual_head_eeg.jpg
   :width: 70%
   :align: center

   Brain activity wit EEG recordings.


.. figure:: screenshots/visualizer_dual_seeg_and_regions.jpg
   :width: 90%
   :align: center

   Brain activity with sEEG recordings (on the left instance) and region level activity (on the right).


Connectivity Measure Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This visualizer can be used for displaying various Brain Connectivity Measures, related to a given Connectivity.

On the X axis, we will see the Connectivity nodes listed, and for each of them, we see the computed measure on the Y axis.

.. figure:: screenshots/visualizer_histogram.jpg
   :width: 90%
   :align: center

   Connectivity Measure Visualizer.


Topographic Visualizer
~~~~~~~~~~~~~~~~~~~~~~

This visualizer can be used for displaying various Brain Connectivity Measures, related to a given Connectivity.
Its input is same as for the previous visualizer (Connectivity Measure Visualizer), but the display is completely different.
Instead of a discrete view, this time, we can have a continous display (with gradients).

.. figure:: screenshots/visualizer_topographic.jpg
   :width: 90%
   :align: center

   Preview for Topographic Visualizer


Surface Visualizer
~~~~~~~~~~~~~~~~~~~~

This visualizer can be used for displaying various Brain Surface. It is a static view,
mainly for visual inspecting imported surfaces in TVB.
Optionally it can display associated RegionMapping entities for a given surface.

.. figure:: screenshots/visualizer_surface.jpg
   :width: 90%
   :align: center

   Surface Visualizer.


Sensor Visualizer
~~~~~~~~~~~~~~~~~~~~

This visualizer can be used for displaying EEG, MEEG, and internal sensors .
It is a static view, intended for visual inspecting imported sensors in TVB.
Optionally it can display the sensors on a EEG cap surface.

To show sensors displaying on a Cap, check the call-out on the top-right corner.

When displaying the EEG sensors on a EEG Cap surface, we are automatically computing a "parcellation".
Currently this parcellation has no anatomical meaning, it is only based on distance (a vertex gets coloured as
the closest sensor).

.. figure:: screenshots/sensors_eeg_meg.jpg
   :width: 90%
   :align: center

   EEG and MEG Sensors.


.. figure:: screenshots/sensors_internal.jpg
   :width: 60%
   :align: center

   Internal Sensors.


Local Connectivity Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Once a Local Connectivity dataTypes (which in fact is a huge sparse matrix of max size surface
vertices x surface vertices, shaped after the cut-off) gets computed, one can view the correlation
of a given vertex compared to all its neighbours, by launching this viewer (from the DataType overlay).

In order to see some correlation, one should pick (by mouse click) a vertex on the 3D cortical
surface once it loads in the canvas.


Group Display
.......................

Discrete PSE Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~

Discrete Parameter Space Exploration View, will show up to two measures of the Simulator results,
after varying input Simulator Parameters. The two displayed measures are emphasized in the node shapes and node colors.

When running a range of Simulations in TVB, it is possible to do it by varying up to 2 input parameters (displayed on
the X and Y axis of current viewer).This visualizer supports to display results when the resulting space is not bigger
than 200 points.

.. figure:: screenshots/simulator_pse_configuration.jpg
   :width: 90%
   :align: center

   Preview for Discrete PSE Visualizer, when varying two input parameters of the simulator

When moving with your mouse cursor over a graph node, you will see a few details about that particular simulation result.
When clicking a node, an overlay window will open, which gives you full access to view or further analyze that
particular Simulation result.

Isocline PSE Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~

Continuous Parameter Space Exploration View, will show the effect of varying Simulator parameters in a continuous form.

When running a range of Simulations in TVB, it is possible to do it by varying up to 2 input parameters (displayed on
the X and Y axis of current viewer). This visualizer supports ranges with 2 dimensions only, it does not support ranges
with only one dimension. Also both varying dimensions need to be numeric parameters (no DataType ranges are supported
for display in this visualizer).

.. figure:: screenshots/simulator_pse_iso.jpg
   :width: 90%
   :align: center

   Preview for Continuous PSE Visualizer, when varying two numeric input parameters of the simulator

Controls for scaling or zooming the graph are available in this viewer. When you click on the coloured area, an overlay
window will open, containing possibility to view or further analyze the simulation result closest to the point where
you clicked.

Analyzers + Visualizers
.......................

Covariance Visualizer
~~~~~~~~~~~~~~~~~~~~~~

Displays the covariance matrix. 
The matrix size is `number of nodes` x `number of nodes`

.. figure:: screenshots/visualizer_covariance.jpg
   :width: 90%
   :align: center

   Preview for Covariance Visualizer



Cross Coherence Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Displays the cross-coherence matrix. Axes represent brain nodes.
The matrix size is `number of nodes` x `number of nodes`.

 
.. figure:: screenshots/visualizer_cross_coherence.jpg
   :width: 90%
   :align: center

   Preview for Cross Coherence Visualizer


Complex Coherence Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Displays the complex-cross-coherence matrix. Axes represent brain nodes.
The matrix is a complex ndarray that contains the `number of nodes` x `number of nodes` cross
spectrum for every frequency frequency and for every segment

This visualizer is very similar with the previous one (Cross Coherence Visualizer).

.. figure:: screenshots/visualizer_complex_coherence.jpg
     :width: 90%
     :align: center

     Preview for Complex Coherence Visualizer


Cross Correlation Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Displays the cross-correlation matrix. Similar to the previous three visualizers.


Pearson Coefficients Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Displays the Pearson correlation coefficients matrix.

.. figure:: screenshots/visualizer_pearson_mplh5.jpg
   :width: 90%
   :align: center

   Preview for Pearson Visualizer (MPLH5)


Fourier Spectrum Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Plots the power spectrum of each node time-series.

.. figure:: screenshots/visualizer_fft.jpg
   :width: 90%
   :align: center

   Preview for Fourier Spectrum Visualizer


Principal Component Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

On the left, the ring plot displays the fraction of the variance that is 
explained by each component.

On the right, the first ten components are plotted against the brain nodes 
(variables). 

.. figure:: screenshots/analyzers_pca.jpg
   :width: 90%
   :align: center

   Preview for Principal Components Analysis Visualizer


Independent Component Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ICA takes time-points as observations and nodes as variables.

As for PCA the TimeSeries datatype must be longer (more time-points) than the number of nodes.
Mostly a problem for TimeSeriesSurface datatypes, which, if sampled at 1024Hz, would need to be greater than
16 seconds long.

.. figure:: screenshots/analyzers_ica.jpg
   :width: 90%
   :align: center

   Preview for Independent Components Analysis Visualizer


Wavelet Spectrogram Visualizer
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

2D representation that shows how the signals wavelet spectral coefficients (frequency) 
vary with time.

.. figure:: screenshots/visualizer_wavelet.jpg
   :width: 90%
   :align: center

   Preview for Wavelet Visualizer

