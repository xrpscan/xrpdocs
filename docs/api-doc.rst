API Doc
=======

.. warning:: The API has many endpoints, but only these endpoints are meant for public use.

The latest (and only) supported API version is ``v1``. All resources are
relative to the following root endpoint::

  https://api.xrpscan.com/api/v1


Get Account
-----------

Get info for a specific Account::

  GET /account/[ACCOUNT_ADDRESS]

Example request:

.. code-block:: shell

    $ curl https://api.xrpscan.com/api/v1/account/rPEPPER7kfTD9w2To4CQk6UCfuHM9c6GDY

Example response:

.. code-block:: json

    {
      "account": "rPEPPER7kfTD9w2To4CQk6UCfuHM9c6GDY",
      "accountName": {
        "account": "rPEPPER7kfTD9w2To4CQk6UCfuHM9c6GDY",
        "domain": "xrptipbot.com",
        "name": "XRP Tip Bot",
        "twitter": "xrptipbot",
        "verified": true
      },
      "inception": "2017-12-13T00:51:52.000Z",
      "initial_balance": 20,
      "ledger_index": 34983099,
      "ownerCount": 292,
      "parent": "rDsbeomae4FXwgQTJp9Rs64Qg9vDiTCdBv",
      "parentName": {
        "account": "rDsbeomae4FXwgQTJp9Rs64Qg9vDiTCdBv",
        "desc": "1",
        "domain": "bitstamp.net",
        "name": "Bitstamp",
        "twitter": "Bitstamp",
        "verified": true
      },
      "previousAffectingTransactionID": "1A182A2763E10063...",
      "previousAffectingTransactionLedgerVersion": 47805749,
      "sequence": 17355,
      "settings": {
        "domain": "xrptipbot.com",
        "emailHash": "833237B8665D2F4E00135E8DE646589F",
        "requireDestinationTag": true
      },
      "tx_hash": "711B7A741B848303F7F77D202D977067806F360...",
      "xrpBalance": "10499.744456"
    }


Get Names
---------

Get list of well-known Names used to identify accounts::

  GET /names/well-known

Example request:

.. code-block:: shell

    $ curl https://api.xrpscan.com/api/v1/names/well-known

Example response:

.. code-block:: json

    [
        {
            "account": "rPEPPER7kfTD9w2To4CQk6UCfuHM9c6GDY",
            "domain": "xrptipbot.com",
            "name": "XRP Tip Bot",
            "twitter": "xrptipbot",
            "verified": true
        },
        {
            "name": "Bitrue",
            "account": "raLPjTYeGezfdb6crXZzcC8RkLBEwbBHJ5",
            "domain": "www.bitrue.com",
            "twitter": "BitrueOfficial",
            "verified": true
        }
    ]


Get Payment flows
-----------------

Get incoming payment flow for a specific Account::

  GET /account/[ACCOUNT_ADDRESS]/payment_flows

Example request:

.. code-block:: shell

    $ curl https://api.xrpscan.com/api/v1/account/rPEPPER7kfTD9w2To4CQk6UCfuHM9c6GDY/payment_flows

Example response:

.. code-block:: json

    [
        {
            "_id": "2019-05-07",
            "volume": 420,
            "payments": 2
        },
        {
            "_id": "2019-05-08",
            "volume": 534,
            "payments": 14
        }
    ]


Get Metrics
-----------

Get XRP Ledger metrics::

  GET /metrics/[metric|type|result]

Example request:

.. code-block:: shell

    $ curl https://api.xrpscan.com/api/v1/metrics/metric

Example response:

.. code-block:: json

    [
      {
        "date": "2019-06-06T00:00:00.000Z",
        "metric": {
          "accounts_created": 2232,
          "exchanges_count": 3381,
          "ledger_count": 22897,
          "ledger_interval": 3.773463772546622,
          "payments_count": 44147,
          "transaction_count": 962376,
          "tx_per_ledger": 42.03065903830196
        }
      },
      {
        "date": "2019-06-07T00:00:00.000Z",
        "metric": {
          "accounts_created": 1912,
          "exchanges_count": 1132,
          "ledger_count": 19310,
          "ledger_interval": 3.7287,
          "payments_count": 40951,
          "transaction_count": 740257,
          "tx_per_ledger": 38.407
        }
      }
    ]

Get Health
----------

Get health of xrpscan's components::

  GET /ping

.. todo:: Only ``api`` property is reliable. ``db``, ``rippled`` and ``validator`` properties are dummy.

Example request:

.. code-block:: shell

    $ curl https://api.xrpscan.com/api/v1/ping

Example response:

.. code-block:: json

    {
      "api": "OK",
      "db": "OK",
      "rippled": "OK",
      "validator": "OK"
    }
