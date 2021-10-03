cmake_minimum_required(VERSION 3.0.0)

set(Name Charlie)

function(print_detail)
  message("Inside function: Before modification: ${Name}")
  set(Name Bob PARENT_SCOPE)
  message("Inside function: After modification: ${Name}")
endfunction()

message("Outside function: Before function call: ${Name}")
print_detail()
message("Outside function: After function call: ${Name}")

# set(Name Charlie)
# message("Root directory: Before adding subdirectory: ${Name}")
# add_subdirectory(demo_subdirectory_scope)
# message("Root directory: After adding subdirectory: ${Name}")

macro(print_macro name_var)
  message("My name is ${name_var}")
  set(name_var abc)
  message("My name is ${name_var}")
endmacro()

print_macro(Charlie)

message("name_var: ${name_var}")