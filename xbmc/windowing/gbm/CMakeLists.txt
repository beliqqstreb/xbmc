set(SOURCES OptionalsReg.cpp
            WinSystemGbm.cpp
            GBMUtils.cpp
            DRMUtils.cpp
            DRMLegacy.cpp
            DRMAtomic.cpp
            OffScreenModeSetting.cpp
            WinSystemGbmEGLContext.cpp
            GBMDPMSSupport.cpp)

set(HEADERS OptionalsReg.h
            WinSystemGbm.h
            GBMUtils.h
            DRMUtils.h
            DRMLegacy.h
            DRMAtomic.h
            OffScreenModeSetting.h
            WinSystemGbmEGLContext.h
            GBMDPMSSupport.h)

if (OPENGL_FOUND)
  list(APPEND SOURCES WinSystemGbmGLContext.cpp)
  list(APPEND HEADERS WinSystemGbmGLContext.h)
endif()
if(OPENGLES_FOUND)
  list(APPEND SOURCES WinSystemGbmGLESContext.cpp)
  list(APPEND HEADERS WinSystemGbmGLESContext.h)
endif()

core_add_library(windowing_Gbm)
