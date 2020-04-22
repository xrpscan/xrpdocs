API Doc
=======

License
-------

.. image:: https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png
  :align: center
  :alt: Creative Commons Attribution-ShareAlike 4.0 International License

XRPSCAN API by `XRPSCAN <https://xrpscan.com/>`_ is licensed under a
`Creative Commons Attribution-ShareAlike 4.0 International License
<http://creativecommons.org/licenses/by-nc-sa/4.0/>`_.
Permissions beyond the scope of this license, including commercial use are
available: :ref:`contact_us`

Introduction
------------

The latest (and only) supported API version is ``v1``. All resources are
relative to the following root endpoint::

  https://api.xrpscan.com/api/v1

.. warning:: The API has many endpoints, but only the following endpoints are 
  meant for public use.

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

.. note:: For Accounts marked as **verified**, verification proof is available with a
  commercial license. Please :ref:`contact_us` for more details.

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


Get Amendments
--------------

Get list of Amendments supported by XRPL::

  GET /amendments

Example request:

.. code-block:: shell

    $ curl https://api.xrpscan.com/api/v1/amendments

Example response:

.. code-block:: json

    [
      {
        "amendment_id": "30CD365592B8EE40489BA01AE2F7555CAC9C983145871DC82A42A31CF5BAE7D9",
        "count": 18,
        "enabled": false,
        "name": "DeletableAccounts",
        "supported": true,
        "threshold": 27,
        "validations": 35,
        "vote": 170,
        "introduced": "1.4.0"
      },
      {
        "amendment_id": "C4483A1896170C66C098DEA5B0E024309C60DC960DE5F01CD7AF986AA3D9AD37",
        "enabled": true,
        "name": "fixMasterKeyAsRegularKey",
        "supported": true,
        "enabled_on": "2019-10-02T07:37:50.000Z",
        "introduced": "1.3.1",
        "tx_hash": "61096F8B5AFDD8F5BAF7FC7221BA4D1849C4E21B1BA79733E44B12FC8DA6EA20"
      },
    ]

Get Amendment
--------------

Get a specific Amendment supported by XRPL::

  GET /amendment/[AMENDMENT_ID]

Example request:

.. code-block:: shell

    $ curl https://api.xrpscan.com/api/v1/amendment/30CD365592B8EE40489BA01AE2F7555CAC9C983145871DC82A42A31CF5BAE7D9

Example response:

.. code-block:: json

    {
      "amendment_id": "30CD365592B8EE40489BA01AE2F7555CAC9C983145871DC82A42A31CF5BAE7D9",
      "count": 18,
      "enabled": false,
      "name": "DeletableAccounts",
      "supported": true,
      "threshold": 27,
      "validations": 35,
      "vote": 170,
      "introduced": "1.4.0",
      "voters": [
        {
          "validation_public_key": "nHUFCyRCrUjvtZmKiLeF8ReopzKuUoKeDeXo3wEUBVSaawzcSBpW",
          "domain": "ripple.kenan-flagler.unc.edu"
        },
        {
          "validation_public_key": "nHDH7bQJpVfDhVSqdui3Z8GPvKEBQpo6AKHcnXe21zoD4nABA6xj",
          "domain": "ripplevalidator.uwaterloo.ca"
        }
      ],
      "vetoers": [
        {
          "validation_public_key": "nHUFE9prPXPrHcG3SkwP1UzAQbSphqyQkQK9ATXLZsfkezhhda3p",
          "domain": "alloy.ee"
        },
        {
          "validation_public_key": "nHUUrjuEMtvzzTsiW2xKinUt7Jd83QFqYgfy3Feb7Hq1EJyoxoSz",
          "domain": "validator.ripple.com"
        }
      ]
    }



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
