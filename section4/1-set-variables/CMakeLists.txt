cmake_minimum_required(VERSION 3.0.0)

# project(module4 VERSION 1.0.0) # will emit error "project command is not scriptable"

message("Hello World")

set(NAME "BOB Smith") # String (= List with 1 item)
# set(NAME BOB Smith) # List
# set(NAME Bob;Smith) # List
# set(NAME "Bob" "Smith") # List
# set(NAME "Bob;Smith") # List
set(HEIGHT 190)

message("Hello, my name is ${NAME}, my height is ${HEIGHT}cm and my age is ${AGE} years")