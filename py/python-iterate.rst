How-To Iterate in Python
========================

Iterate keys only
-----------------

.. code:: python

   d = {'x': 1, 'y': 2, 'z': 3}
   for key in d:
       print(key, 'corresponds to', d[key])

Iterate keys and values:
------------------------

.. code:: python

   d = {'x': 1, 'y': 2, 'z': 3}
   for key, value in d.items():
       print(key, 'corresponds to', value)
