set( VerticalTabs_SRCS
    verticaltabsplugin.cpp
    verticaltabscontroller.cpp
    verticaltabswidget.cpp
    verticaltabssettings.cpp
    tabtreeview.cpp
    tabtreedelegate.cpp
    loadinganimator.cpp
    tabfiltermodel.cpp
    tablistview.cpp
    tablistdelegate.cpp
    verticaltabsschemehandler.cpp
)

ecm_create_qm_loader( VerticalTabs_SRCS falkon_verticaltabs_qt )

set( VerticalTabs_UIS
    verticaltabssettings.ui
)
qt5_wrap_ui(UIS ${VerticalTabs_UIS})

set( VerticalTabs_RSCS
    verticaltabs.qrc
)
qt5_add_resources(RSCS ${VerticalTabs_RSCS})

add_library(VerticalTabs MODULE ${VerticalTabs_SRCS} ${UIS} ${RSCS})
install(TARGETS VerticalTabs DESTINATION ${FALKON_INSTALL_PLUGINDIR})
target_link_libraries(VerticalTabs FalkonPrivate)
