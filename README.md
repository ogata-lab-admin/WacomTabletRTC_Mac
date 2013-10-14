#About WacomTabletRTC_Mac
WacomTabletRTC_Mac is OpenRTM-aist's RT-Component using Qt 4.7.4 tablet exsample. 

#before build
change  `/Library/Frameworks/QtCore.framework/Versions/4/Headers/qglobal.h`

In gloval.h, find these block

    #  if !defined(MAC_OS_X_VERSION_10_7)
    #     define MAC_OS_X_VERSION_10_7 MAC_OS_X_VERSION_10_6 + 1
    #  endif

under `#  endif `, add

    #  if !defined(MAC_OS_X_VERSION_10_7)
    #     define MAC_OS_X_VERSION_10_7 MAC_OS_X_VERSION_10_6 + 1
    #  endif
    #  if !defined(MAC_OS_X_VERSION_10_8)
    #     define MAC_OS_X_VERSION_10_8 MAC_OS_X_VERSION_10_7 + 1
    #  endif

then change
`if (MAC_OS_X_VERSION_MAX_ALLOWED > MAC_OS_X_VERSION_10_8)`
    

ref: <http://stevenyue.com/2011/10/27/install-pyqt4-qt-4-7-on-mac-osx-lion/>

#How to build
    $qmake -spec macx-g++
    $make

