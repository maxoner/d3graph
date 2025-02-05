Big Bang network
''''''''''''''''''''

Default
--------------------------------------------------

.. code:: python

	from d3graph import d3graph
	size = [10, 20, 10, 10, 15, 10, 5]

	# Initialize
	d3 = d3graph()
	# Load example
	adjmat, _ = d3.import_example('bigbang')
	# Process adjmat
	d3.graph(adjmat)
	# Show
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_default.html" height="700px" width="850px", frameBorder="0"></iframe>


Node colors
------------

.. code:: python

	d3.set_node_properties(color=adjmat.columns.values)
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_color.html" height="700px" width="850px", frameBorder="0"></iframe>


Node fontcolors
----------------

.. code:: python

	d3.set_node_properties(color='cluster', fontcolor='node_color')
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_text_color.html" height="700px" width="850px", frameBorder="0"></iframe>



Node sizes
----------

.. code:: python

	d3.set_node_properties(color=adjmat.columns.values, size=size)
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_color_size.html" height="700px" width="850px", frameBorder="0"></iframe>

Edge sizes
----------

.. code:: python

	d3.set_node_properties(color=adjmat.columns.values, size=size, edge_size=size[::-1])
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_color_size_edge.html" height="700px" width="850px", frameBorder="0"></iframe>


Edge colors
-----------

.. code:: python

	d3.set_node_properties(color=adjmat.columns.values, size=size, edge_size=size[::-1], edge_color='#00FFFF')
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_color_size_edge_color.html" height="700px" width="850px", frameBorder="0"></iframe>


Colormap
-----------

.. code:: python

	d3.set_node_properties(color=adjmat.columns.values, size=size, edge_size=size[::-1], edge_color='#00FFFF', cmap='Set2')
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_cmap.html" height="700px" width="850px", frameBorder="0"></iframe>


Directed arrows
----------------------

.. code:: python

	d3.set_edge_properties(directed=True)
	d3.set_node_properties(color=adjmat.columns.values, size=size, edge_size=size, edge_color='#000FFF', cmap='Set1')
	d3.show()

.. raw:: html

   <iframe src="https://erdogant.github.io/docs/d3graph/d3graph/bigbang_directed.html" height="700px" width="850px", frameBorder="0"></iframe>


Karate Club network
''''''''''''''''''''

.. code:: python

	from d3graph import d3graph

	# Initialize
	d3 = d3graph()
	# Load karate example
	adjmat, df = d3.import_example('karate')

	label = df['label'].values
	node_size = df['degree'].values

	d3.graph(adjmat)
	d3.set_node_properties(color=df['label'].values)
	d3.show()

	d3.set_node_properties(label=label, color=label, cmap='Set1')
	d3.show()

	d3.set_node_properties(size=node_size)
	d3.show()

	d3.set_node_properties(color=label, size=node_size)
	d3.show()

	d3.set_edge_properties(edge_distance=100)
	d3.set_node_properties(color=node_size, size=node_size)
	d3.show()

	d3 = d3graph(charge=1000)
	d3.graph(adjmat)
	d3.set_node_properties(color=node_size, size=node_size)
	d3.show()

	d3 = d3graph(collision=1, charge=250)
	d3.graph(adjmat)
	d3.set_node_properties(color=label, size=node_size, edge_size=node_size, cmap='Set1')
	d3.show()

	d3 = d3graph(collision=1, charge=250)
	d3.graph(adjmat)
	d3.set_node_properties(color=label, size=node_size, edge_size=node_size, edge_color='#00FFFF', cmap='Set1')
	d3.show()


Hide Slider
''''''''''''''''''''

The slider can be hidden from the output HTML by setting the ``show_slider=False`` parameter.

.. code:: python

	from d3graph import d3graph

	# Initialize
	d3 = d3graph()
	# Load example
	adjmat, df = d3.import_example('karate')
	# Process adjmat
	d3.graph(adjmat)
	d3.show(show_slider=False)




.. include:: add_bottom.add