target_include_directories(${EXEC_NAME} PRIVATE .)

target_sources(${EXEC_NAME} PRIVATE
        ./weatherapi.h
        ./weatherapi.cpp
        #./ApiKeyManager.cpp
        #./ApiKeyManager.h
        #HttpRequest.cpp
        #HttpRequest.h
)
