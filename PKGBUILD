# Script generated with Bloom
pkgdesc="ROS - This package provides foot step generation for the thormang3."
url='http://wiki.ros.org/thormang3_foot_step_generator'

pkgname='ros-kinetic-thormang3-foot-step-generator'
pkgver='0.2.0_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-generation'
'ros-kinetic-robotis-controller-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-std-msgs'
'ros-kinetic-thormang3-walking-module-msgs'
)

depends=('ros-kinetic-cmake-modules'
'ros-kinetic-geometry-msgs'
'ros-kinetic-message-runtime'
'ros-kinetic-robotis-controller-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-roslib'
'ros-kinetic-std-msgs'
'ros-kinetic-thormang3-walking-module-msgs'
)

conflicts=()
replaces=()

_dir=thormang3_foot_step_generator
source=()
md5sums=()

prepare() {
    cp -R $startdir/thormang3_foot_step_generator $srcdir/thormang3_foot_step_generator
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

