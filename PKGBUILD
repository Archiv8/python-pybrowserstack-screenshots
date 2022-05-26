#!/bin/bash

# Created from the original PKGBUILD by Caleb Maclennan <caleb@alerque.com> and Guillaume Horel <guillaume.horel@gmail.com>

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# ToDo: Add files: User documentation
# ToDo: Add files: Tooling
# FixMe: Namcap warnings and errors

# Maintainer: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>
# Contributor: Ross Clark <https://github.com/Archiv8/python-pyclipper/discussions>

_langname="python"
_relname="pybrowserstack-screenshots"

pkgname="${_langname}-${_relname}"
pkgver=0.1
pkgrel=2
pkgdesc='A client and api wrapper for Browserstack Screenshots, including phantomCSS support'
arch=(
  "any"
)
url="http://github.com/cmck/$_pkgname"
license=(
  "MIT"
)
depends=(
  "python"
  "python-pillow"
  "python-requests"
  "python-simplejson"
)
makedepends=(
  "python-setuptools"
)
_zipname="${_relname}-${pkgver}"
source=(
  "https://files.pythonhosted.org/packages/source/${_relname::1}/${_relname}/${_zipname}.tar.gz"
)
sha512sums=(
  '19ce920468938bd8733d3abdd18ce0b19e93a3f9079246192a8e4b4437cfea93368ce32e836d368f4e381e38cfa2b86f321dadd940f5be89adcd9728452f3263'
)

build() {

  cd "${_zipname}"

  python setup.py build
}

package() {

  cd "${_zipname}"

  python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
