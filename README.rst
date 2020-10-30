Long Connections
----------------

Zeek normally logs connections at the end of the connection, but this 
can cause trouble for incident responders in the case of very long 
lived connections that end up being unknown to defenders until too
late.

This package provides a new log named `conn_long` which will log 
"intermediate" conn logs for long connections. It's logged into
a separate log stream to avoid confusing the semantics of the normal
Zeek conn log which users can assume only contains "complete" 
connections.

The script will also generate a `LongConnection::found` notice 
whenever it discovers a long connection.

Installation
------------

::

	zkg refresh
	zkg install zeek/corelight/bro-long-connections
