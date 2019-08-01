# CMakeLists for Intan RHD2000 Electroplating

if(WIN32)
  set(GUI_TYPE WIN32)
elseif(APPLE)
  set(GUI_TYPE MACOSX_BUNDLE)
endif()

set(RHD2000EPLATE_SRC
    boardcontrol.cpp
    boardcontrol.h
    common.cpp
    common.h
    configurationparameters.h
    configurationwindow.cpp
    configurationwindow.h
    dataprocessor.cpp
    dataprocessor.h
    electrodeimpedance.h
    electroplatingboardcontrol.cpp
    electroplatingboardcontrol.h
    globalconfigurationwindow.cpp
    globalconfigurationwindow.h
    globalconstants.h
    globalparameters.h
    impedancehistoryplot.cpp
    impedancehistoryplot.h
    impedancemeasurecontroller.cpp
    impedancemeasurecontroller.h
    impedanceplot.cpp
    impedanceplot.h
    main.cpp
    mainwindow.cpp
    mainwindow.h
    okFrontPanelDLL.cpp
    okFrontPanelDLL.h
    oneelectrode.cpp
    oneelectrode.h
    presentimpedancesplot.cpp
    presentimpedancesplot.h
    rhd2000config.cpp
    rhd2000config.h
    rhd2000datablock.cpp
    rhd2000datablock.h
    rhd2000evalboard.cpp
    rhd2000evalboard.h
    rhd2000registers.cpp
    rhd2000registers.h
    saveformat.cpp
    saveformat.h
    settings.h
    signalchannel.cpp
    signalchannel.h
    signalgroup.cpp
    signalgroup.h
    signalprocessor.cpp
    signalprocessor.h
    signalsources.cpp
    signalsources.h
    significantround.cpp
    significantround.h
    streams.cpp
    streams.h
)

add_executable(rhd2000electroplating
    ${GUI_TYPE}
    ${RHD2000EPLATE_SRC}
)

target_link_libraries(rhd2000electroplating
    ${CMAKE_DL_LIBS}
    Qt5::Widgets
    Qt5::Multimedia
)

install(TARGETS rhd2000electroplating DESTINATION ${CMAKE_INSTALL_BINDIR})

# Windows stuff
if ("${CMAKE_SYSTEM_NAME}" STREQUAL "Windows")
   add_definitions("-D_UNICODE" "-DUNICODE")
   set_target_properties(rhd2000electroplating PROPERTIES LINK_FLAGS_DEBUG "/SUBSYSTEM:CONSOLE")
   set_target_properties(rhd2000electroplating PROPERTIES COMPILE_DEFINITIONS_DEBUG "_CONSOLE")
   set_target_properties(rhd2000electroplating PROPERTIES LINK_FLAGS_RELWITHDEBINFO "/SUBSYSTEM:windows")
   set_target_properties(rhd2000electroplating PROPERTIES LINK_FLAGS_RELEASE "/SUBSYSTEM:windows")
   set_target_properties(rhd2000electroplating PROPERTIES LINK_FLAGS_MINSIZEREL "/SUBSYSTEM:windows")
endif()
