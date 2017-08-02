skelcd-control-leanos
=====================

[![Travis Build](https://travis-ci.org/yast/skelcd-control-leanos.svg?branch=master)](https://travis-ci.org/yast/skelcd-control-leanos)


Installation control file for SUSE Linux Enterprise LeanOS product

See also the [documentation for the `control.xml` file][1].

[1]: https://github.com/yast/yast-installation/blob/master/doc/control-file.md

## How It Works

LeanOS adds the capability to install independent products with the same media.

It has its own control.xml file which has reasonable defaults for almost all except partitioning.

Its workflow ends up with a product selection client, and there is where comes to play the
installation.xml specific product file. It is a common add-on installation xml that can do everything
an add-on can do. You can read more about the add-on installation.xml in
[this document](https://github.com/yast/yast-installation/blob/master/doc/control-file.md#control-sectionadd-on-product-installation-workflow-specification).

But LeanOS is a product itself so apart of the control.xml file it also has its own installation.xml.

Product selector in installator basically search for any product. Then for each product it try to
find package that provides `system-installation() = <product_name>`. If such package does not exist,
it removes product from selection. When product is selected, then coresponding package that
provides system installation for given project is unpacked and its installation.xml is used
to continue with installation.
