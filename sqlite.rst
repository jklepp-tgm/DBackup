SQLite
======

For our diploma project SQLite is used for storing metadata about recordings.
Besides storing additional information, the SQLite database is also used to
determinate which recordings already were synced to the central server.

Data in the SQLite database does not necessarily have a schema known when
designing the software. Instead a key-value store is build on top of the SQLite
database. This results in a rather simple database scheme but a high number of
CRUD (Create, Read, Update, Delete) operations.

.. image:: _static/SQLite_ERD.png
	:width: 20%

.. code:: sql

	CREATE TABLE IF NOT EXISTS entries (
		uid INT,
		name,
		value,
		PRIMARY KEY (uid, name));
