cmake_minimum_required(VERSION 2.4)

#
# Examples
#


SET(EXAMPLE_DIRS
  Tracker
  Imager
  Status
  Receiver
  Thread
  Lab_PWP/NowyKlient
  Lab_PWP/NowySerwer
  )

if (${OpenIGTLink_PROTOCOL_VERSION} GREATER 1)
  SET(EXAMPLE_DIRS
    ${EXAMPLE_DIRS}
    ImageMeta
    Point
    TrackingData
    QuaternionTrackingData
    ImageDatabaseServer
    String
    Bind
    PolyData
    Capability
    Trajectory
    SessionManager
    )
endif (${OpenIGTLink_PROTOCOL_VERSION} GREATER 1)

## Imager program isn't supported by QNX
if(NOT OpenIGTLink_PLATFORM_QNX)
  SUBDIRS(
    ${EXAMPLE_DIRS}  
    )
else(NOT OpenIGTLink_PLATFORM_QNX)
  SUBDIRS(
      Tracker
      Status
      Receiver
      )
endif(NOT OpenIGTLink_PLATFORM_QNX)



