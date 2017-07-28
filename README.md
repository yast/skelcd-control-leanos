skelcd-control-leanos
=====================

[![Travis Build](https://travis-ci.org/yast/skelcd-control-leanos.svg?branch=master)](https://travis-ci.org/yast/skelcd-control-leanos)


Installation control file for SUSE Linux Enterprise LeanOS product

See also the [documentation for the `control.xml` file][1].

[1]: https://github.com/yast/yast-installation/blob/master/doc/control-file.md

## How It Works

LeanOS integrate multiple previously independ products. LeanOS have its control.xml file
which have reasonable defaults, except partitioning. And its workflow ends up with product selection client.
And here comes into play product specific installation.xml. It is common add-on installation xml, that can do
everythin any add-on can do. Also LeanOS can be installed itself, so it have its control.xml and
also installation.xml . For add-on installation.xml documentation see
[documentation](https://github.com/yast/yast-installation/blob/master/doc/control-file.md#control-sectionadd-on-product-installation-workflow-specification).

Product selector in installator basically search for any product. Then for each product it try to
find package that provides `system-installation() = <product_name>`. If such package does not exist,
it removes product from selection. When product is selected, then coresponding package that
provides system installation for given project is unpacked and its installation.xml is used
to continue with installation.
