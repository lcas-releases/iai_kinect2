^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package kinect2_bridge
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.0.10 (2019-11-26)
-------------------
* added opencl dep
* Contributors: Marc Hanheide

0.0.9 (2018-07-24)
------------------
* Changed readme.md file in kinect2_bridge
* Contributors: Manuel Fernandez-Carmona

0.0.8 (2018-07-24)
------------------
* Libfreenect2 dev (`#2 <https://github.com/LCAS/iai_kinect2/issues/2>`_)
  * Changed freenect2 from submodule to subproject with git. catkin_make_isolated --install works
  * m.ch.
  * added git as a dependence and install targets
  * w.i.p.
  * Update CMakeLists.txt
  * freenect2 moved to its own fork
  * Works in my docker...
* Contributors: Manuel Fernandez-Carmona

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
* pre flight commit
* Moved libfreenect to its own package
* removed invalid package
* resolving deps
* libfreenect2 compiles as an external project from kinect2_bridge
* Merge pull request `#352 <https://github.com/LCAS/iai_kinect2/issues/352>`_ from Tobias-Fischer/master
  Add KDE depth unwrapping support
* Change help()
* Update README.md
* Add KDE support
* fixed PR
* Merge pull request `#343 <https://github.com/LCAS/iai_kinect2/issues/343>`_ from MRASL/roslaunch_output
  allow configuring screen output
* allow configuring screen output
* kinect2_bridge starts streams depending on the subscribed topics.
  If for example no color topic is subscribed then the processing of color frames in libfreenect2 is disabled.
  Updated kinect2_bridge to libfreenect v0.2.0.
  Updated README.
* Merge pull request `#244 <https://github.com/LCAS/iai_kinect2/issues/244>`_ from code-iai/libfreenect2_v0.2_api
  Libfreenect2 v0.2 api cleanup
* fixed status check.
  added lock for color frame for sd registration.
* prepared kinect2_bridge for libfreenect2 v0.2 API changes.
  status of frames is checked.
  format of frames is checked.
  added code to handle RGBA and BGRA.
* fixed a typo
* Merge branch 'ahundt-master' into devel
* CMake build fixes for OS X for CL.h based on equivalent fixes in libfreenect2
* Added naming of threads.
* Added hints for new default installation location for libfreenect2.
  Added a note for what to do, when installed somewhere else to the README.
* kinect2_bridge releases frames from libfreenect2 as fast as possible now.
* added support for libfreenect2 CUDA depth processor.
* delete kinect2_bridge object, if not started correctly.
* Added checks for start/stop return values.
  Updated README.
* added depth_image_proc as run dependency, because it is needed by the launch file.
* Merge branch 'master' into devel
* Merge pull request `#215 <https://github.com/LCAS/iai_kinect2/issues/215>`_ from delftrobotics/add-tf-depend
  Add missing dependency on tf.
* Add missing dependency on tf.
* added a normal node version for kinect2_bridge and an argument to choose either the nodelet or the node version.
* added respan as an argument of the launch file, with default to false.
  if the kinect2_bridge dies, or did not start up correctly the launch file will terminate.
  the nodelet is now throwing an expection, when start up did not work.
* Improved FAQ and fixed some spelling mistakes.
* updated READMEs
* Prepared compatibility to OpenCV 3.
  Still only works with OpenCV 2.4.8 because cv_bridge needs it in Indigo/Jade.
* Merge branch 'xlz-use-new-api' into devel
* Use new libfreenect2 API
  libfreenect2 API no longer exports details about
  DepthPacketProcessor. Use Freenect2Device::setConfiguration()
  instead.
* removed unused variable.
* more meaningful output message.
* used color to highlight certain parts of the console output.
* Switched to ros_console for output.
  Added colored output.
* Fixed a bug that could lead to segfaults when CXX11 in libfreenect2 is enabled and time between received frames is greater that a second.
* fix for crash introduced in commit ff3758f29719428c645cc4f8a7934d75abfbb7c0
* removed OpenMP, because it is not used.
* Fixed possible deallocation of frame data before processing finised.
* added camera parameters that are just used for the depth to color registration.
  the ir camera paramters are set to the default default camera parameters, to prevent bad results in sd registration.
* fixed starting of processing even if initialization failed.
  take care of freeing memory if initialization failed.
* improved READMEs.
* Updated to new BGRA color image format in libfreenect2.
* registration api of libfreenect2 has changed.
* replaced depth_registration with new name kinect2_registration.
* To fit catkin_make
* fixed missing base_name in kinect2_bridge nodelet parameters.
* renamed depth_registration package to kinect2_registration.
  renamed registration_viewer package to kinect2_viewer.
* Added support for the color to depth registration from libfreenect2.
  Changed base name for ir/depth topics to `sd`.
  Added point cloud for sd depth/color.
  Fixed bug with wrong tf frames for some images.
  Fixed bug with rviz not soppurting MONO16, but TYPE_8UC1.
* updated READMEs.
* Changed topic structure. Topics are now grouped by resolution and share the same camera_info.
  Updated README.
* kinect2bridge stops kinect device if no topics are subscribed and restarts it as soon as clients connect to topics.
* Merge commit 'refs/pull/81/head' of github.com:code-iai/iai_kinect2 into devel
  Conflicts:
  kinect2_bridge/launch/kinect2_bridge.launch
  kinect2_bridge/src/kinect2_bridge.cpp
* switched back to base_name.
* changed calibration and added an example for depth calibration.
* fix bug for serial number with leading 0
* added default namespace to node initialization if node is started without a namespace set.
* kinect2_bridge uses now ros namespaces instead of base_name.
* simplified tf broadcaster. Just publishing optical frame of ir and rgb.
* changed output messages form the message itself to pointer to it, to enable zero copy transfer to nodelets.
* Simplified compression. Only one topic for compressed images. Special "compressedDepth" topic is only needed if floating point images need to be compressed, which is not the case for kinect2_bridge.
  This also solves an issue with rviz (which is a bug in DepthCloud plugin from rviz), where no compression for the color image is choose able if depth image does not have the same compression topics.
* set queue size 5
* add machine tag if statement
* Added a default distance of 52 mm between color and ir if no calibration data is provided.
  added additional foreground check run to depth registration.
* added fix for reduced color frame rate when cpu load is high and depth processing takes longer than new frames to arrive.
  worker threads with even thread id will first check for depth frames, while the ones with odd ids will first check color frames.
* flip images only if necessary.
  for depth and ir apply flipping after conversion to 16 bit (faster).
* nodelet manager name can now be passed as an argument to the launch file.
  added argument to disable start of own nodelet manager if kinect2_bridge should use an external nodelet manager.
  added machine tag to nodelet manager.
* removed static transform publisher launch file, because functionality is now inside kinect2_bridge.
* added a nodelet wrapper for kinect2_bridge.
  added all parameters of kinect2_bridge as arguments for the launch file.
  the launch file created a nodelet manager for kinect2_bridge_nodelet and point cloud nodelets.
* fixed default values for bilateral and edge aware filter.
  added information on processing time for color and depth.
* added number of threads for image processing as a parameter.
  cleaned up CMakeLists.txt.
* Merge pull request `#48 <https://github.com/LCAS/iai_kinect2/issues/48>`_ from airballking/master
  Added argument for machine to launch-file kinect2_bridge.
* Added argument for machine to launch-file kinect2_bridge.
* fix for sensor serial not beeing parsed.
  changed name of node in lauch file to the defined base_name.
* switched back to upstream libfreenect2.
  updated documentation.
* base name for topics is now modifiable to support multiple kinect2 on one roscore.
  all parameter are now handled by ros.
  integrated a static tf publisher that uses the calibration results.
  updated the launch file.
* decoupled receiving of depth and color frames, so that each is published with their maximum frequency.
  added synchronization of timestamps so that the exact time message filtering works.
* added configuration of depth packet processor.
* added depth calibration to calibration tool.
  added depth shift parameter to kinect2_bridge.
  added documentation and results for depth calibration to README.
  removed duplicated definitions.
* added fps info to kinect2_bridge terminal output.
  reduced cpu load when using fps limiter.
* replaced absolute links to destinations inside the repo to relative links.
* updated documentation
* use find_package to find glfw.
  added check for cpu depth registration.
* methods for depth registration and processing can now be chosen by command line parameters.
  opengl depth processor is now working again.
* added a cmake config file for depth_registration.
  checking available depth_registration methods in kinect2_bridge.
  renamed cmake_modules to cmake.
* added fall back if libfreenect2 was not build with CXX11 support.
  it can happen that kinect2_bridge hangs up, if libfreenect2 is not receiving frames.
* removed CONFIG from find_package to support older cmake versions.
* fixed dependency for hydro.
* updated package dependencies.
* added listing of kinect2 devices.
  added check for validity of provided serial.
* use libfreenect2 config file instead of additional defines.
* added point cloud publisher to kinect2 launch file.
  thanks to Stefanie.
* added possibility to select opencl device for depth processing.
* added parameter to select openCL device for depth registration.
* added option to use TIFF as compression method for 16Bit images like depth and ir.
  TIFF is much faster but the compression ratio is less good.
* build type is not set explicitly anymore.
  if c++11 check faild it give an error.
  removed unused cmake option from viewer.
* jpg compression level is changeable through parameter.
  used best png depth compression settings (compression ratio / processing time).
* removed opencv remap using opencl.
* simplified depth registration.
  fixed a small bug in CPU based registration.
  renamed some constants.
* updated README.
  changes freenect2_INCLUDE_DIR to freenect2_INCLUDE_DIRS.
* added check for c++11 flag support.
  switched to upstream libfreenect2.
  added option for using libfreenect2 opencl packet pipeline.
* Merge pull request `#25 <https://github.com/LCAS/iai_kinect2/issues/25>`_ from ibec-robotics/master
  Added the possibility to select a camera using the -cam parameter along the serial number
* Added the possibility to select a camera using the -cam parameter along the serial number of the camera
* added option to use TIFF as compression method for 16Bit images like depth and ir.
  TIFF is much faster but the compression ratio is less good.
* build type is not set explicitly anymore.
  if c++11 check faild it give an error.
  removed unused cmake option from viewer.
* jpg compression level is changeable through parameter.
  used best png depth compression settings (compression ratio / processing time).
* removed opencv remap using opencl.
* simplified depth registration.
  fixed a small bug in CPU based registration.
  renamed some constants.
* updated README.
  changes freenect2_INCLUDE_DIR to freenect2_INCLUDE_DIRS.
* added check for c++11 flag support.
  switched to upstream libfreenect2.
  added option for using libfreenect2 opencl packet pipeline.
* added minimum value for number of worker threads if std::thread::hardware_concurrency() is not returning any valid value.
  added cmake options for using opencl depth registration and rectification.
* renamed camera_calibration to kinect2_calibration because a package with this name already exists in image_pipeline.
* Removed leading slash from tf frames. tf2 does not like that
* Added possibility to launch the kinect with tf
* added key binding information to the READMEs.
* all files now visible inside qtcreator.
* moved starting of libfreenect device to initialization.
  removed unused calibration file entries from loading.
  added output of default camera parameters and the ones loaded from the calibration files.
* improved information on permissions
* added more information to READMEs
* added more information to readmes
* moved kinect2 related tools into a new repository.
* Contributors: Andre Phu-Van Nguyen, Andrew Hundt, Georg Bartels, Jan-Hendrik Worch, Jordi, Kenta Yonekura, Lingzhu Xiang, Maarten de Vries, Marc Hanheide, Peter KT Yu, Thiemo Wiedemeyer, Tobias Fischer, mfernandezcarmona@lincoln.ac.uk, wkentaro
