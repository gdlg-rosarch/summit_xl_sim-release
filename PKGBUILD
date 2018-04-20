# Script generated with Bloom
pkgdesc="ROS - The summit_xl_sim metapackage"
url='http://ros.org/wiki/summit_xl_sim'

pkgname='ros-kinetic-summit-xl-sim'
pkgver='1.0.9_3'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-summit-xl-control'
'ros-kinetic-summit-xl-gazebo'
'ros-kinetic-summit-xl-robot-control'
'ros-kinetic-summit-xl-sim-bringup'
)

conflicts=()
replaces=()

_dir=summit_xl_sim
source=()
md5sums=()

prepare() {
    cp -R $startdir/summit_xl_sim $srcdir/summit_xl_sim
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

