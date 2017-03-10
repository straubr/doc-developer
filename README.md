OTRS Developer's Manual
===========================

This repository contains the sources of the OTRS developer manual.
They are located in en/ and stored in docbook format.


How to Generate HTML from the Sources
-------------------------------------

You need to install the xsltproc and docbook-xsl packages (names may vary depending
on your distribution).

Then you can run

```
cd /tmp
xsltproc --xinclude /usr/share/xsl/docbook-xsl/html/chunk.xsl /path/to/doc-developer/en/book.xml
```

The paths may vary, on MacOS docbook-xsl is located in /opt/local/xsl/...


How to Validate the Sources
---------------------------

You need to install the xmllint and docbook-xml packages.

Then you can run
```
xmllint --postvalid --nonet --xinclude --noout /path/to/doc-developer/en/book.xml
```

If you don't see any output, the validation was successful.


Generating Translation Sources Manually
---------------------------------------

If you add any new files, make sure to include them in `po4a.conf`.

Then you can run
```
po4a -v -k0 /path/to/doc-developer/po4a.conf
```

The command will generate files for all supported languages.
