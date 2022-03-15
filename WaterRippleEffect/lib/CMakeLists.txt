# -------------------------------------------------------------------------------------------------
# Set Library (Water Ripple Effect Lib)
# -------------------------------------------------------------------------------------------------
project(WaterRippleEffectLib)


# -------------------------------------------------------------------------------------------------
# Add a library with the above sources
# -------------------------------------------------------------------------------------------------
add_library(${PROJECT_NAME}
    "${CMAKE_CURRENT_LIST_DIR}/src/Engine/WaterRippleEffect.cpp"
    "${CMAKE_CURRENT_LIST_DIR}/src/Engine/WaterRippleEffect.h"
  )

# -------------------------------------------------------------------------------------------------
# Include Path
# -------------------------------------------------------------------------------------------------
target_include_directories(
    ${PROJECT_NAME} PUBLIC
        "${CMAKE_CURRENT_LIST_DIR}/src"
  )

# -------------------------------------------------------------------------------------------------
# Set Alias of Library to reach from parent executeable
# -------------------------------------------------------------------------------------------------
add_library(sub::WaterRippleEffectLib ALIAS ${PROJECT_NAME})