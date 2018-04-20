# Script generated with Bloom
pkgdesc="ROS - object_recognition_ros_visualization contains rviz plugins to visualize ork detection results"
url='wg-perception.github.io/object_recognition_ros'

pkgname='ros-kinetic-object-recognition-ros-visualization'
pkgver='0.3.8_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('boost'
'ros-kinetic-catkin'
'ros-kinetic-object-recognition-msgs'
'ros-kinetic-object-recognition-ros'
'ros-kinetic-pluginlib'
'ros-kinetic-rviz'
)

depends=('boost'
'ros-kinetic-object-recognition-msgs'
'ros-kinetic-object-recognition-ros'
'ros-kinetic-pluginlib'
'ros-kinetic-rviz'
)

conflicts=()
replaces=()

_dir=object_recognition_ros_visualization
source=()
md5sums=()

prepare() {
    cp -R $startdir/object_recognition_ros_visualization $srcdir/object_recognition_ros_visualization
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

