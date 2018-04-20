# Script generated with Bloom
pkgdesc="ROS - A simple script that aggregates all of the topics that a &quot;pr2_dashboard&quot; app might be interested in."
url='http://ros.org/wiki/pr2_dashboard_aggregator'

pkgname='ros-lunar-pr2-dashboard-aggregator'
pkgver='1.12.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-lunar-catkin'
)

depends=('ros-lunar-pr2-msgs'
'ros-lunar-rospy'
'ros-lunar-std-msgs'
)

conflicts=()
replaces=()

_dir=pr2_dashboard_aggregator
source=()
md5sums=()

prepare() {
    cp -R $startdir/pr2_dashboard_aggregator $srcdir/pr2_dashboard_aggregator
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

