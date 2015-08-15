# Maintainer: DavidK <david_king at softhome dot net>
# Contributor:  veox <box 55 [shift-two] mail [dot] ru>

pkgname=cl-hunchentoot
_clname=hunchentoot
pkgver=1.2.27
pkgrel=1
pkgdesc="A Common Lisp webserver and toolkit for building dynamic sites"
arch=('any')
url="http://www.weitz.de/hunchentoot/"
license=('BSD')
depends=('common-lisp' 'cl-base64' 'cl-bordeaux-threads' 'cl-chunga' 'cl-fad' 'cl-flexi-streams' 'cl-md5' 'cl-ppcre' 'cl-rfc2388' 'cl-ssl' 'cl-usocket' 'cl-trivial-backtrace')
optdepends=('cl-who: for the example code' \
            'cl-drakma: for the tests')
install=cl-hunchentoot.install
options=('docs')
source=('http://weitz.de/files/hunchentoot.tar.gz')
#The sources from that website change md5sums, more often than daily, without
#change in content. We have to trust it's not really changing.
md5sums=('SKIP')

package() {
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}/test
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}/url-rewrite
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}/www
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}/www/errors
    install -d "${pkgdir}"/usr/share/common-lisp/source/${_clname}/www/img
    install -d "${pkgdir}"/usr/share/common-lisp/systems
    install -d "${pkgdir}"/usr/share/licenses/${pkgname}
    install -d "${pkgdir}"/usr/share/doc/${pkgname}

    cd "${srcdir}"/${_clname}-${pkgver}

    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname} \
        *.lisp
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname}/test \
        test/*
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname}/url-rewrite \
        url-rewrite/*
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname}/www \
        www/*.ico www/h* www/index*
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname}/www/errors \
        www/errors/*
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname}/www/img \
        www/img/*
    install -m 644 -t "${pkgdir}"/usr/share/common-lisp/source/${_clname} \
        *.asd
    install -m 644 doc/LICENSE.txt \
        "${pkgdir}"/usr/share/licenses/${pkgname}
    install -m 644 -t "${pkgdir}"/usr/share/doc/${pkgname} doc/*i*

    cd "${pkgdir}"/usr/share/common-lisp/systems
    ln -s ../source/${_clname}/${_clname}.asd .
}

# vim:set ts=2 sw=4 et nospell:
