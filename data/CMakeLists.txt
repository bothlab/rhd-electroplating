 
# .desktop file
install(FILES rhd2000electroplating.desktop DESTINATION "${CMAKE_INSTALL_DATADIR}/applications")

# icon
install(FILES rhd2000electroplating.svg DESTINATION "${CMAKE_INSTALL_DATADIR}/icons/hicolor/scalable/apps/")

# Rhythm bitfile
install(FILES rhythm/main.bit DESTINATION "${CMAKE_INSTALL_DATADIR}/intan/rhd2000electroplating/")
