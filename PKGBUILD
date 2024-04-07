# Maintainer: Harry Gifford <hegiax@outlook.com>

pkgname=python-jaxlib-rocm-bin
pkgver=0.4.25
pkgrel=1
pkgdesc='Pre-built JAX'
arch=('x86_64')
url='https://github.com/ROCm/jax'
license=('Apache')
groups=('jax')
depends=('python-absl'
         'python-flatbuffers'
         'python-ml-dtypes'
         'python-numpy'
         'python-scipy')
makedepends=('python-installer')
_py=cp311
conflicts=('python-jaxlib')
provides=("python-jaxlib=${pkgver}")
source=("${url}/releases/download/jaxlib-v${pkgver}/jaxlib-${pkgver}+rocm600-${_py}-${_py}-manylinux2014_${arch}.whl")
b2sums=("aa85a49043c0a92351a6dc2446993765e0cf57a944b5ee1b795b30d92efbda33cdf81d2203f67355fc7d986572471a6791eb93a4513bd0bb73e1aaa065c62d00")

package() {
    python -m installer \
        --compile-bytecode 1 \
        --destdir $pkgdir \
        "jaxlib-${pkgver}+rocm600-${_py}-${_py}-manylinux2014_${arch}.whl"
    cd "${srcdir}/jaxlib-${pkgver}+rocm600.dist-info/"
    install -vDm644 -t "${pkgdir}/usr/share/licenses/${pkgname}" LICENSE.txt
}
