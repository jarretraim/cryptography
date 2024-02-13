Software Bill of Materials (SBOM) for pyca/cryptography
=======================================================

A Software Bill of Materials (SBOM) is allow consumers of a software project
to gain visibility into the libraries and dependencies of the project. This 
information can be critical in vulnerabilty and incident management as well
as ensuring license compliance and other needs. 

There seem to be three competing standards for SBOM generation as of early
2024. These are:

1. `CycloneDX`_ - An `OWASP`_ project.
2. `SWID`_ - A NIST standard.
3. `SPDX`_ - A Linux Foundation project. 



CycloneDX offers two software packages - the main cyclonedx package that 
generates Cyclone compatible BOM JSON files as well as the cyclone CLI
that enables the processing and conversion of the files to other formats.

In our case, we use the main CycloneDX implementation to create our 
SBOM reports. We then use the Cyclone CLI to convert that data into
other formats. 

NOTE: Some conversations (CSV, SPDX, etc) may be lossy.

The SBOM files are named according to the following format:

``cryptography-<cryptography-version>.sbom.<standard>.<standard-version>.<format>``

* ``<cryptography-version>`` - The version of the cryptography library this SBOM is valid for.
* ``<standard>`` - The SBOM standard in use - currently ``cyclonedx`` and ``spdx``.
* ``<standard-version>`` - The version of the Cyclone or SPDX format being used.
* ``<format>`` - The format of the output file - generally json, csv or xml.


.. _`CycloneDX`: https://cyclonedx.org/
.. _`SWID`: https://csrc.nist.gov/projects/Software-Identification-SWID
.. _`SPDX`: https://spdx.dev/
.. _`OWASP`: https://owasp.org/