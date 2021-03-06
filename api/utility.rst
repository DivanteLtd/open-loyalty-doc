Utility API
===========

These endpoints will allow you to see the CSVs in Open Loyalty.



Get CSV of customers assigned to a specific level
-------------------------------------------------

To retrieve a CSV of customers assigned to a level, you need to call the ``/api/<storeCode>/csv/level/<level>`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET /api/<storeCode>/csv/level/<level>

+----------------------------------+----------------+------------------------------------------------------------------+
| Parameter                        | Parameter type |  Description                                                     |
+==================================+================+==================================================================+
| Authorization                    | header         | Token received during authentication                             |
+----------------------------------+----------------+------------------------------------------------------------------+
| <storeCode>                      | query          | Code of the store to get CSV of customers.                       |
+----------------------------------+----------------+------------------------------------------------------------------+
| <level>                          | query          |  Level ID                                                        |
+----------------------------------+----------------+------------------------------------------------------------------+

Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/csv/level/000096cf-32a3-43bd-9034-4df343e5fd93 \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    "First name","Last name","E-mail address",Gender,Telephone,"Loyalty card number",Birthdate,"Created at","Legal agreement","Marketing agreement","Data processing agreement"
    John,Doe,user@example.com,male,11111,,"1990-09-11 02:00:00","2016-08-08 10:53:14",,,
    Jane,Doe,user-temp@example.com,male,111112222,0000,"1990-09-11 02:00:00","2016-08-08 10:53:14",,,
    alina,test,qwe@test.pl,male,1212121212,,"2018-03-19 00:00:00","2018-02-19 14:24:18",1,,
    Tomasz,Test7,tomasztest7@wp.pl,,,,,"2018-02-20 08:21:39",1,,
    user,user,user@user.pl,male,123456789876543,,"2018-02-23 00:00:00","2018-02-23 13:29:11",1,,

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.



Get CSV of customers assigned to a specific segment
---------------------------------------------------

To retrieve a CSV of customers assigned to a segment, you need to call the ``/api/<storeCode>/csv/segment/<segment>`` endpoint with the ``GET`` method.

Definition
^^^^^^^^^^

.. code-block:: text

    GET /api/<storeCode>/csv/segment/<segment>

+----------------------+----------------+--------------------------------------------------------+
| Parameter            | Parameter type |  Description                                           |
+======================+================+========================================================+
| Authorization        | header         | Token received during authentication                   |
+----------------------+----------------+--------------------------------------------------------+
| <storeCode>          | query          | Code of the store to get CSV of customers.             |
+----------------------+----------------+--------------------------------------------------------+
| <segment>            | query          | Segment ID                                             |
+----------------------+----------------+--------------------------------------------------------+


Example
^^^^^^^

.. code-block:: bash

    curl http://localhost:8181/api/DEFAULT/csv/segment/63afec60-5e74-43fc-a5e1-81bbc03421ca \
        -X "GET" \
        -H "Accept: application/json" \
        -H "Content-type: application/x-www-form-urlencoded" \
        -H "Authorization: Bearer eyJhbGciOiJSUzI1NiIsInR5cCI6..."

Example Response
^^^^^^^^^^^^^^^^

.. code-block:: text

    STATUS: 200 OK

.. code-block:: json

    "First name","Last name","E-mail address",Gender,Telephone,"Loyalty card number",Birthdate,"Created at","Legal agreement","Marketing agreement","Data processing agreement"

.. note::

    The *eyJhbGciOiJSUzI1NiIsInR5cCI6...* authorization token is an example value.
    Your value may be different. Read more about Authorization :doc:`here </api/authorization>`.
