cmake_minimum_required(VERSION 3.13) # target_link_options
#cmake_minimum_required(VERSION 3.16) # target_precompile_headers

project(OpenFrameworks_CMake)

set(OF_DIR /opt/openFrameworks)
set(OF_LIBS_ROOT_DIR "${OF_DIR}/libs")
set(OF_SRC_DIR "${OF_DIR}/libs/openFrameworks")

add_library(openFrameworks STATIC
  ${OF_SRC_DIR}/utils/ofTimer.cpp
  ${OF_SRC_DIR}/utils/ofXml.cpp
  ${OF_SRC_DIR}/utils/ofThread.cpp
  ${OF_SRC_DIR}/utils/ofSystemUtils.cpp
  ${OF_SRC_DIR}/utils/ofFileUtils.cpp
  ${OF_SRC_DIR}/utils/ofUtils.cpp
  ${OF_SRC_DIR}/utils/ofMatrixStack.cpp
  ${OF_SRC_DIR}/utils/ofURLFileLoader.cpp
  ${OF_SRC_DIR}/utils/ofLog.cpp
  ${OF_SRC_DIR}/utils/ofFpsCounter.cpp
  ${OF_SRC_DIR}/graphics/ofTrueTypeFont.cpp
  ${OF_SRC_DIR}/graphics/ofImage.cpp
  ${OF_SRC_DIR}/graphics/ofCairoRenderer.cpp
  ${OF_SRC_DIR}/graphics/ofPath.cpp
  ${OF_SRC_DIR}/graphics/ofGraphics.cpp
  ${OF_SRC_DIR}/graphics/of3dGraphics.cpp
  ${OF_SRC_DIR}/graphics/ofBitmapFont.cpp
  ${OF_SRC_DIR}/graphics/ofPixels.cpp
  ${OF_SRC_DIR}/graphics/ofTessellator.cpp
  ${OF_SRC_DIR}/graphics/ofGraphicsBaseTypes.cpp
  ${OF_SRC_DIR}/graphics/ofRendererCollection.cpp
  ${OF_SRC_DIR}/video/ofVideoGrabber.cpp
  ${OF_SRC_DIR}/video/ofGstUtils.cpp
  ${OF_SRC_DIR}/video/ofVideoPlayer.cpp
  ${OF_SRC_DIR}/video/ofGstVideoGrabber.cpp
  ${OF_SRC_DIR}/video/ofGstVideoPlayer.cpp
  ${OF_SRC_DIR}/communication/ofSerial.cpp
  ${OF_SRC_DIR}/communication/ofArduino.cpp
  ${OF_SRC_DIR}/app/ofAppNoWindow.cpp
  ${OF_SRC_DIR}/app/ofMainLoop.cpp
  ${OF_SRC_DIR}/app/ofAppGLFWWindow.cpp
  ${OF_SRC_DIR}/app/ofAppGlutWindow.cpp
  ${OF_SRC_DIR}/app/ofAppRunner.cpp
  ${OF_SRC_DIR}/app/ofBaseApp.cpp
  ${OF_SRC_DIR}/events/ofEvents.cpp
  ${OF_SRC_DIR}/sound/ofSoundBaseTypes.cpp
  ${OF_SRC_DIR}/sound/ofSoundBuffer.cpp
  ${OF_SRC_DIR}/sound/ofOpenALSoundPlayer.cpp
  ${OF_SRC_DIR}/sound/ofSoundPlayer.cpp
  ${OF_SRC_DIR}/sound/ofFmodSoundPlayer.cpp
  ${OF_SRC_DIR}/sound/ofRtAudioSoundStream.cpp
  ${OF_SRC_DIR}/sound/ofSoundStream.cpp
  ${OF_SRC_DIR}/math/ofMath.cpp
  ${OF_SRC_DIR}/math/ofMatrix3x3.cpp
  ${OF_SRC_DIR}/math/ofMatrix4x4.cpp
  ${OF_SRC_DIR}/math/ofQuaternion.cpp
  ${OF_SRC_DIR}/math/ofVec4f.cpp
  ${OF_SRC_DIR}/math/ofVec2f.cpp
  ${OF_SRC_DIR}/gl/ofMaterial.cpp
  ${OF_SRC_DIR}/gl/ofShader.cpp
  ${OF_SRC_DIR}/gl/ofLight.cpp
  ${OF_SRC_DIR}/gl/ofFbo.cpp
  ${OF_SRC_DIR}/gl/ofGLUtils.cpp
  ${OF_SRC_DIR}/gl/ofGLRenderer.cpp
  ${OF_SRC_DIR}/gl/ofTexture.cpp
  ${OF_SRC_DIR}/gl/ofVboMesh.cpp
  ${OF_SRC_DIR}/gl/ofBufferObject.cpp
  ${OF_SRC_DIR}/gl/ofVbo.cpp
  ${OF_SRC_DIR}/gl/ofGLProgrammableRenderer.cpp
  ${OF_SRC_DIR}/types/ofColor.cpp
  ${OF_SRC_DIR}/types/ofParameter.cpp
  ${OF_SRC_DIR}/types/ofParameterGroup.cpp
  ${OF_SRC_DIR}/types/ofRectangle.cpp
  ${OF_SRC_DIR}/types/ofBaseTypes.cpp
  ${OF_SRC_DIR}/3d/of3dUtils.cpp
  ${OF_SRC_DIR}/3d/ofNode.cpp
  ${OF_SRC_DIR}/3d/of3dPrimitives.cpp
  ${OF_SRC_DIR}/3d/ofCamera.cpp
  ${OF_SRC_DIR}/3d/ofEasyCam.cpp
  )

set_property(TARGET openFrameworks PROPERTY CXX_STANDARD 14)
target_include_directories(openFrameworks PUBLIC
  /usr/include/cairo
  /usr/include/glib-2.0
  /usr/lib/glib-2.0/include
  /usr/include/pixman-1
  /usr/include/freetype2
  /usr/include/libpng16
  /usr/include/harfbuzz
  /usr/include/gstreamer-1.0
  /usr/include/orc-0.4
  /usr/include/AL
  /usr/include/rtaudio
  /usr/include/gtk-3.0
  /usr/include/pango-1.0
  /usr/include/fribidi
  /usr/include/gdk-pixbuf-2.0
  /usr/include/libmount
  /usr/include/blkid
  /usr/include/gio-unix-2.0
  /usr/include/atk-1.0
  /usr/include/at-spi2-atk/2.0
  /usr/include/dbus-1.0
  /usr/lib/dbus-1.0/include
  /usr/include/at-spi-2.0
  )

target_include_directories(openFrameworks PUBLIC
  # ${OF_DIR}/libs/fmodex/include
  ${OF_DIR}/libs/glm/include
  ${OF_DIR}/libs/glm/include/glm
  ${OF_DIR}/libs/glm/include/glm/simd
  ${OF_DIR}/libs/glm/include/glm/gtx
  ${OF_DIR}/libs/glm/include/glm/gtc
  ${OF_DIR}/libs/glm/include/glm/ext
  ${OF_DIR}/libs/glm/include/glm/detail
  ${OF_DIR}/libs/json/include
  ${OF_DIR}/libs/kiss/include
  ${OF_DIR}/libs/pugixml/include
  ${OF_DIR}/libs/tess2/include
  ${OF_DIR}/libs/utf8/include
  ${OF_DIR}/libs/utf8/include/utf8
  ${OF_SRC_DIR}
  ${OF_SRC_DIR}/utils
  ${OF_SRC_DIR}/graphics
  ${OF_SRC_DIR}/video
  ${OF_SRC_DIR}/communication
  ${OF_SRC_DIR}/app
  ${OF_SRC_DIR}/events
  ${OF_SRC_DIR}/sound
  ${OF_SRC_DIR}/math
  ${OF_SRC_DIR}/gl
  ${OF_SRC_DIR}/types
  ${OF_SRC_DIR}/3d
  )

target_compile_definitions(openFrameworks PUBLIC
  __LINUX_ALSA__
  __LINUX_PULSE__
  __UNIX_JACK__
  )

target_compile_definitions(openFrameworks PUBLIC
  GCC_HAS_REGEX
  OF_USING_GTK
  OF_USING_MPG123
  )

target_compile_definitions(openFrameworks PUBLIC
  _REENTRANT
  )

target_compile_options(openFrameworks PUBLIC
  "-pthread"
  )

target_link_directories(openFrameworks INTERFACE
  # ${OF_DIR}/libs/fmodex/lib/linux64/
  )

target_link_libraries(openFrameworks INTERFACE
  # fmodex
  ${OF_DIR}/libs/kiss/lib/linux64/libkiss.a
  ${OF_DIR}/libs/tess2/lib/linux64/libtess2.a
  gstapp-1.0
  gstvideo-1.0
  gstbase-1.0
  gstreamer-1.0
  udev
  fontconfig
  freetype
  sndfile
  openal
  curl
  glfw
  rtaudio
  jack
  pulse-simple
  pulse
  asound
  GLEW
  X11
  GLU
  GL
  gtk-3
  gdk-3
  z
  pangocairo-1.0
  pango-1.0
  harfbuzz
  atk-1.0
  cairo-gobject
  cairo
  gdk_pixbuf-2.0
  gio-2.0
  gobject-2.0
  glib-2.0
  mpg123
  glut
  X11
  Xrandr
  Xxf86vm
  Xi
  Xcursor
  dl
  pthread
  freeimage
  boost_filesystem
  boost_system
  pugixml
  uriparser
  Xinerama
  )

target_link_options(openFrameworks INTERFACE
  -Wl,--as-needed
  -Wl,--gc-sections
  -fuse-ld=gold
  )

set_property(TARGET openFrameworks PROPERTY CXX_STANDARD 11)

############################################################

add_executable(${CMAKE_PROJECT_NAME}
  ${CMAKE_CURRENT_SOURCE_DIR}/src/ofApp.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp
  )

target_link_libraries(${CMAKE_PROJECT_NAME} PRIVATE openFrameworks)

# target_precompile_headers(helloWorld
#   PRIVATE <ofMain.h>
#   )

set_property(TARGET ${CMAKE_PROJECT_NAME} PROPERTY CXX_STANDARD 11)
