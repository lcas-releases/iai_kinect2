^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package kinect2_calibration
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.0.9 (2018-07-24)
------------------

0.0.8 (2018-07-24)
------------------

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
* Merge pull request `#467 <https://github.com/LCAS/iai_kinect2/issues/467>`_ from dipendras/master
  added calibration functionality using asymmetric circle
* Merge pull request `#427 <https://github.com/LCAS/iai_kinect2/issues/427>`_ from eisoku9618/add-converter
  Add a convert script from calib_pose.yaml to urdf format
* Merge pull request `#418 <https://github.com/LCAS/iai_kinect2/issues/418>`_ from furushchev/patch-1
  Fix broken README.md
* added calibration functionality using asymmetric circle
* Update README.md
  fix syntax error.
* Add a convert script from calib_pose.yaml to urdf format
* Merge pull request `#1 <https://github.com/LCAS/iai_kinect2/issues/1>`_ from eisoku9618/fix-readme
  Fix broken README.md
* Fix broken README.md
* Merge pull request `#315 <https://github.com/LCAS/iai_kinect2/issues/315>`_ from awhampton/typo_fix
  fixed typos
* fixed typos
* Merge pull request `#278 <https://github.com/LCAS/iai_kinect2/issues/278>`_ from mintar/patch-1
  Update dead links in kinect2_calibration/README.md
* Update dead links in kinect2_calibration/README.md
* fix for changed parameter of solvePNPRansac in OpenCV 3.
* Merge branch 'ahundt-master' into devel
* CMake build fixes for OS X for CL.h based on equivalent fixes in libfreenect2
* Merge branch 'fjonath1-master' into devel
* Fix for OSX
* Improved FAQ and fixed some spelling mistakes.
* Prepared compatibility to OpenCV 3.
  Still only works with OpenCV 2.4.8 because cv_bridge needs it in Indigo/Jade.
* more meaningful output message.
* Added more checks for invalid data and provided more error messages.
* Switched to ros_console for output.
  Added colored output.
* improved READMEs.
* To fit catkin_make
* renamed depth_registration package to kinect2_registration.
  renamed registration_viewer package to kinect2_viewer.
* Added support for the color to depth registration from libfreenect2.
  Changed base name for ir/depth topics to `sd`.
  Added point cloud for sd depth/color.
  Fixed bug with wrong tf frames for some images.
  Fixed bug with rviz not soppurting MONO16, but TYPE_8UC1.
* Changed topic structure. Topics are now grouped by resolution and share the same camera_info.
  Updated README.
* kinect2bridge stops kinect device if no topics are subscribed and restarts it as soon as clients connect to topics.
* Merge commit 'refs/pull/81/head' of github.com:code-iai/iai_kinect2 into devel
  Conflicts:
  kinect2_bridge/launch/kinect2_bridge.launch
  kinect2_bridge/src/kinect2_bridge.cpp
* switched back to base_name.
* removed warning
* fix bug when using acircle
* kinect2_bridge uses now ros namespaces instead of base_name.
* Simplified compression. Only one topic for compressed images. Special "compressedDepth" topic is only needed if floating point images need to be compressed, which is not the case for kinect2_bridge.
  This also solves an issue with rviz (which is a bug in DepthCloud plugin from rviz), where no compression for the color image is choose able if depth image does not have the same compression topics.
* Update README.md
* Update README.md
  fixed meaning of raw in the pictures
* Update README.md
  Added examples of uncalibrated vs calibrated images.
* Update README.md
  Added an image about the typical calibration setup.
* Update README.md
  fixed typo
* Update README.md
* added note to calibration instructions
* changed calibration and viewer to be anonymous nodes.
* added support for variable base name.
* updated documentation.
* added depth calibration to calibration tool.
  added depth shift parameter to kinect2_bridge.
  added documentation and results for depth calibration to README.
  removed duplicated definitions.
* updated README.
* added function that checks the order of color and ir points for sync calibration and orders them in the same way.
  added parameter to use 8 instead of 5 coefficients.
* minor changes to ir image preparation
* improved ir image processing for calibration.
  fixed ir value range setting.
* updated documentation
* added controls to adjust ir range.
* added different chessboard patterns.
* fixed dependency for hydro.
* added receiving and storing of depth images to calibration tool.
  depth images might be of use later for a depth calibration.
* updated package dependencies.
* build type is not set explicitly anymore.
  if c++11 check faild it give an error.
  removed unused cmake option from viewer.
* fixed issue calibration not responding to ctrl+c when waiting for first images.
* added check for c++11 flag support.
  switched to upstream libfreenect2.
  added option for using libfreenect2 opencl packet pipeline.
* build type is not set explicitly anymore.
  if c++11 check faild it give an error.
  removed unused cmake option from viewer.
* fixed issue calibration not responding to ctrl+c when waiting for first images.
* added check for c++11 flag support.
  switched to upstream libfreenect2.
  added option for using libfreenect2 opencl packet pipeline.
* added minimum value for number of worker threads if std::thread::hardware_concurrency() is not returning any valid value.
  added cmake options for using opencl depth registration and rectification.
* renamed camera_calibration to kinect2_calibration because a package with this name already exists in image_pipeline.
* Contributors: Alexis Maldonado, Andrew Hundt, Dip, Felix Jonathan, Ferenc Balint-Benczedi, Furushchev, Kenta Yonekura, Marc Hanheide, Martin Günther, Peter KT Yu, Thiemo Wiedemeyer, ahampton, eisoku9618, mfernandezcarmona@lincoln.ac.uk, 修昊
