if(CONFIG_TFLITE_MICRO_LIB)
  # Mark TFLM as an imported library
  add_library(tflm STATIC IMPORTED)
  set_target_properties(tflm PROPERTIES
    IMPORTED_LOCATION ${CMAKE_CURRENT_SOURCE_DIR}/lib/libtflm.a
  )

  # Mark muriscv_nn as an imported library
  add_library(muriscv_nn STATIC IMPORTED)
  set_target_properties(muriscv_nn PROPERTIES
    IMPORTED_LOCATION ${CMAKE_CURRENT_SOURCE_DIR}/lib/libmuriscv_nn.a
  )

  # Link them to the Zephyr app
  zephyr_link_libraries(tflm)
  zephyr_link_libraries(muriscv_nn)
endif()
