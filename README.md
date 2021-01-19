skelcd-control-leanos
=====================

[![Workflow Status](https://github.com/yast/skelcd-control-leanos/workflows/CI/badge.svg?branch=master)](
https://github.com/yast/skelcd-control-leanos/actions?query=branch%3Amaster)


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

The product selector dialog in the installation displays all products for which exists a `system-installation() = <product_name>` provides dependency.
When a product is selected then its corresponding package providing the system installation is unpacked
and its `installation.xml` file is used to continue with the installation.
