# Script generated with import_catkin_packages.py
# For more information: https://github.com/bchretien/arch-ros-stacks
pkgdesc="ROS - The controller manager."
url='https://github.com/ros-controls/ros_control/wiki'

pkgname='ros-noetic-controller-manager'
pkgver='0.20.0'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=1
license=('BSD')

ros_makedepends=(
    ros-noetic-catkin
    ros-noetic-controller-interface
    ros-noetic-controller-manager-msgs
    ros-noetic-hardware-interface
    ros-noetic-pluginlib
    ros-noetic-rostest
)

makedepends=(
    cmake
    ros-build-tools
    ${ros_makedepends[@]}
    python-setuptools
)

ros_depends=(
    ros-noetic-roscpp
    ros-noetic-controller-interface
    ros-noetic-controller-manager-msgs
    ros-noetic-hardware-interface
    ros-noetic-pluginlib
    ros-noetic-std-msgs
    ros-noetic-rosparam
    ros-noetic-rospy
)

depends=(
    ${ros_depends[@]}
)

_dir="ros_control-${pkgver}/controller_manager"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-controls/ros_control/archive/${pkgver}.tar.gz")
sha256sums=('28adcdf8e410bcee60415eebd8087f7b5c60af9833df9a75120e0250a7e459e8')

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}
