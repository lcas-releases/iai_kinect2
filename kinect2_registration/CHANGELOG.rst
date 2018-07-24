^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package kinect2_registration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.0.7 (2018-07-23)
------------------

0.0.6 (2018-07-19 20:08)
------------------------

0.0.5 (2018-07-19 18:46)
------------------------

0.0.4 (2018-07-19 18:34)
------------------------

0.0.3 (2018-07-19 18:33)
------------------------

0.0.2 (2018-07-19 14:51)
------------------------
* changelogs
* changelogs
* libfreenect2 compiles as an external project from kinect2_bridge
* Merge pull request `#465 <https://github.com/LCAS/iai_kinect2/issues/465>`_ from christian-rauch/enable_exceptions
  enable exceptions
* enable exceptions
* fixed catkin_tools dependency issues with OpenCL.
  added additional instructions to CUDA installation.
* changes EIGEN3_FOUND to uppercase letters.
* Merge pull request `#294 <https://github.com/LCAS/iai_kinect2/issues/294>`_ from v4hn/eigen-include-dir
  use different cmake variable for eigen include dir
* use different cmake variable for eigen include dir
  Eigen3.2's upstream FindEigen3.cmake specifies only
  EIGEN3_INCLUDE_DIR, not EIGEN3_INCLUDE_DIRS:
  https://bitbucket.org/eigen/eigen/src/cafa6d909f409f4ec33070ebf991a77e7b747dc1/cmake/FindEigen3.cmake?at=default&fileviewer=file-view-default#FindEigen3.cmake-10
  Eigen3.3-beta provides an Eigen3Config that defines
  EIGEN3_INCLUDE_DIRS AND _DIR, but that's still beta, even though
  Ubuntu introduced it in xenial already. So to stay backwards
  compatible, _INCLUDE_DIR should be used.
* fix for renamed opencl header in opencl 2.0
* fixed warnings on 16.04
* updated instructions for OpenCL in README.
  removed intel beignet fix. Issue is sloved with beignet 1.1.1, which is available at a ppa now.
* Merge pull request `#244 <https://github.com/LCAS/iai_kinect2/issues/244>`_ from code-iai/libfreenect2_v0.2_api
  Libfreenect2 v0.2 api cleanup
* fix for a problem of Beignet with enqueueReadBuffer and an event vector as parameter
* fixed indentation
* Merge branch 'ahundt-master' into devel
* CMake build fixes for OS X for CL.h based on equivalent fixes in libfreenect2
* Added pinned memory output buffer to improve reading registered depth from GPU.
* Fixed changed name of OpenCL_FOUND in CMakeLists.txt.
* Added profiling code for OpenCL.
  Fixed macros.
* improved OpenCL error macros.
* merged OpenCL compatibility changes form libfreenect2 into kinect2_registration.
* Merge branch 'fjonath1-master' into devel
* Fix for OSX
* Improved FAQ and fixed some spelling mistakes.
* Prepared compatibility to OpenCV 3.
  Still only works with OpenCV 2.4.8 because cv_bridge needs it in Indigo/Jade.
* fixed small bug which could lead to segfaults in opencl.
* used color to highlight certain parts of the console output.
* Switched to ros_console for output.
  Added colored output.
* checking each individual opencl call on success instead of using exceptions.
* fixed bug in opencl registration on 32 bit systems.
* To fit catkin_make
* renamed depth_registration package to kinect2_registration.
  renamed registration_viewer package to kinect2_viewer.
* Contributors: Andrew Hundt, Christian Rauch, Felix Jonathan, Ferenc Balint-Benczedi, Kenta Yonekura, Marc Hanheide, Michael Görner, Thiemo Wiedemeyer, mfernandezcarmona@lincoln.ac.uk
