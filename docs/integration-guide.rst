Integration Guide
=================

Do you work at a Bank, Financial Institution or a Cryptocurrency Exchange? Its 
easy to integrate XRP Scan in your application. We support deep links for
**Accounts**, **Transactions**, **Ledgers**, **Amendments** and **Validator nodes**.
All pages support desktop as well as mobile layouts.

Account
-------

To link to an Account, use::

    https://xrpscan.com/account/[ACCOUNT_ADDRESS]

``ACCOUNT_ADDRESS`` in the XRP Ledger is identified by an address in the Base58
format. An `Account address <https://developers.ripple.com/basic-data-types.html#addresses>`_ 
has the following properties:

- A string of length between 25 to 35 characters. 
- Starts with the character ``r``.
- Is case sensitive.
- Uses alphanumeric characters, excluding the number ``0`` capital letter 
  ``O``, capital letter ``I``, and lowercase letter ``l``.

Example: https://xrpscan.com/account/rGeyCsqc6vKXuyTGF39WJxmTRemoV3c97h


Transaction
-----------

To link to a Transaction, use::

    https://xrpscan.com/tx/[TRANSACTION_HASH]

``TRANSACTION_HASH`` in the XRP Ledger is identified by a 64 charcters long
string. A `Transaction hash <https://developers.ripple.com/basic-data-types.html#hashes>`_ 
has the following properties:

- A string exactly 64 characters in length.
- Hex character set: ``0-9`` and ``A-F``.
- Not case sensitive, but typically written in upper case letters.

Example: `https://xrpscan.com/tx/5A9E938DB7DA6193446A383898C7A66518E9FCE... <https://xrpscan.com/tx/5A9E938DB7DA6193446A383898C7A66518E9FCE65DFFD82DF0B7E65844F3EB61>`_


Ledger
------

To link to a Ledger, use::

    https://xrpscan.com/ledger/[LEDGER_INDEX]

``LEDGER_INDEX`` in the XRP Ledger is identified by a 32 bit unsigned integer.
string. A `Ledger index <https://developers.ripple.com/basic-data-types.html#ledger-index>`_ 
has the following properties:

- A number between 32,570 and 4,294,967,295.
- Must be less than the last closed ledger index.

Example: https://xrpscan.com/ledger/44023993


Validator node
--------------

To link to a Validator node, use::

    https://xrpscan.com/validator/[VALIDATOR_PUBLIC_KEY]

``VALIDATOR_PUBLIC_KEY`` in the XRP Ledger is identified by upto 53 charcters
long string in Base68 format. A `Validator public key <https://developers.ripple.com/data-api.html#public-keys>`_ 
has the following properties:

- A string in Base58, upto 53 characters in length.
- Starts with the character ``n``, commonly followed by ``H``.
- Is case sensitive.
- Uses alphanumeric characters, excluding the number ``0`` capital letter 
  ``O``, capital letter ``I``, and lowercase letter ``l``.

Example: `https://xrpscan.com/validator/nHDB2PAPYqF86j9j3c6w1F1ZqwvQfiWc... <https://xrpscan.com/validator/nHDB2PAPYqF86j9j3c6w1F1ZqwvQfiWcFShZ9Pokg9q4ohNDSkAz>`_

Amendment
---------

To link to an Amendment, use::

    https://xrpscan.com/amendment/[AMENDMENT_ID]

``AMENDMENT_ID`` in the XRP Ledger is identified by upto 64 charcters
long string. An `Amendment ID <https://xrpl.org/known-amendments.html>`_ 
has the following properties:

- A string exactly 64 characters in length.
- Hex character set: ``0-9`` and ``A-F``.
- Case sensitive.


Example: `https://xrpscan.com/amendment/30CD365592B8EE40489BA01AE2F7555C... <https://xrpscan.com/amendment/30CD365592B8EE40489BA01AE2F7555CAC9C983145871DC82A42A31CF5BAE7D9>`_
