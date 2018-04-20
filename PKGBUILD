# Script generated with Bloom
pkgdesc="ROS - This package contains the description (mechanical, kinematic, visual, etc.) of the PR2 robot. The files in this package are parsed and used by a variety of other components. Most users will not interact directly with this package."
url='http://ros.org/wiki/pr2_description'

pkgname='ros-lunar-pr2-description'
pkgver='1.12.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('gtest'
'ros-lunar-catkin'
'ros-lunar-convex-decomposition'
'ros-lunar-ivcon'
'urdfdom'
)

depends=('ros-lunar-xacro'
)

conflicts=()
replaces=()

_dir=pr2_description
source=()
md5sums=()

prepare() {
    cp -R $startdir/pr2_description $srcdir/pr2_description
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

