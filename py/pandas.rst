Pandas
======

-  `Indexing and selecting
   data <https://pandas.pydata.org/pandas-docs/stable/user_guide/indexing.html>`__
-  `Using iloc, loc, &
   ix <https://www.shanelynn.ie/select-pandas-dataframe-rows-and-columns-using-iloc-loc-and-ix/>`__
-  Iterating Dataframes

   -  `iterrows <https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iterrows.html>`__
   -  `itertuples <https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.itertuples.html>`__
   -  `iteritems <https://pandas.pydata.org/pandas-docs/version/0.17.0/generated/pandas.DataFrame.iteritems.html>`__

Display Data
------------

Display all Columns in Jupyter Notebook
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: python

   pd.options.display.max_columns = None

Filter Data
-----------

Remove Duplicates
~~~~~~~~~~~~~~~~~

Remove all duplicates and keep first (inplace).

.. code:: python

   df.drop_duplicates(inplace=True, keep='first')

Only consider certain columns for identifying duplicates and keep first
(inplace).

.. code:: python

   df.drop_duplicates(<list_of_cols>, inplace=True, keep='first')

Remove complete Column
~~~~~~~~~~~~~~~~~~~~~~

Do this inplace.

.. code:: python

   df.drop(<col_name>, axis=1, inplace=True)

Remove rows on Condition
~~~~~~~~~~~~~~~~~~~~~~~~

Do this inplace.

.. code:: python

   df.drop(df[df[<col_name>] == <condition>].index , inplace=True)

Filter nan Values
~~~~~~~~~~~~~~~~~

``nan == nan`` is always ``false``. That is why we can not use ``==`` to
check for ``nan``-values. Use ``pd.isnull(obj : scalar or array-like)``
instead or ``isnull()``. Examples:

.. code:: python

   df.loc[pd.isnull(df['col'])]
   df[df['col'].isnull()]

Change DataFrames
-----------------

Rename Columns
~~~~~~~~~~~~~~

This is renaming the columns inplace. It returns nothing.

::

   df.rename(columns={'A': 'x'}, inplace=True)

Load and save
-------------

Save to CSV
~~~~~~~~~~~

Here without row names (index) ``index=False``.

.. code:: python

   df.to_csv(<path_or_buffer>, index=False)

also see:
https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_csv.html

Load from CSV
~~~~~~~~~~~~~

.. code:: python

   df = pd.read_csv(
           <path_or_buffer>,
           sep=';',
           encoding='us-ascii',
           usecols=<col_list>,
           nrows=<number_of_rows_to_read>,
           )
