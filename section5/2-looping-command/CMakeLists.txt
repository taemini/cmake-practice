cmake_minimum_required(VERSION 3.0.0)

# foreach(x RANGE 10 20 3)
#   message(${x})
# endforeach()

set(VAR1 0;1)
set(VAR2 2 3)
set(VAR3 "4 5")

foreach(x IN LISTS VAR1 VAR2 VAR3)
  message(x = ${x})
endforeach()