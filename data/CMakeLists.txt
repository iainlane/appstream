# CMakeLists for UAI data directory

find_program (LC_INTLTOOL_MERGE intltool-merge)
mark_as_advanced (LC_INTLTOOL_MERGE)

if (LC_INTLTOOL_MERGE STREQUAL "LC_INTLTOOL_MERGE-NOTFOUND")
	message (FATAL_ERROR "Intltool was not found! Please install it to continue!")
endif (LC_INTLTOOL_MERGE STREQUAL "LC_INTLTOOL_MERGE-NOTFOUND")

install(FILES appstream.conf
	DESTINATION ${CMAKE_INSTALL_SYSCONFDIR}
)

install(FILES org.freedesktop.appstream.cli.metainfo.xml
	DESTINATION ${CMAKE_INSTALL_METAINFODIR}
)
