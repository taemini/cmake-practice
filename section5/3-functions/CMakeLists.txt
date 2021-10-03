cmake_minimum_required(VERSION 3.0.0)

# without arguments
function(print_detail1)
  message("My name is Bob")
endfunction()

print_detail1() # My name is Bob

# with arguments
function(print_detail2 name_var)
  message("My name is ${name_var}")
endfunction()

print_detail2(Charlie) # My name is Charlie

set(Name Alice)
print_detail2(Name) # My name is Name
print_detail2(${Name}) # My name is Alice

# double dereference
function(print_detail3 name_var)
  message("My name is ${${name_var}}")
endfunction()

print_detail3(Name) # My name is Alice

# application
set(Name2 Tommy)
set(Age 30)
function(print_detail4 var)
  message("My ${var} is ${${var}}")
endfunction()

print_detail4(Name) # My Name is Tommy
print_detail4(Age) # My Age is 30

# overwrite
function(print_detail1)
  message("My new name is Sponge Bob")
endfunction()

print_detail1() # My new name is Sponge Bob
_print_detail1() # My name is Bob
# (undescore붙이면 overwrite되기전 함수 호출, _는 1개까지만)

# optional arguments
function(print_detail5 name_var)
  message("My name is ${${name_var}}")
  if(DEFINED ARGV1)
    message("Hello, my name is ${ARGV1}")
  endif()

  message("ARGC=  ${ARGC}")
  message("ARGV=  ${ARGV}")
  message("ARGN=  ${ARGN}")
  if(DEFINED ARGV0)
    message("ARGV0=  ${ARGV0}")
  endif()
  if(DEFINED ARGV1)
    message("ARGV1=  ${ARGV1}")
  endif()
  if(DEFINED ARGV2)
    message("ARGV2=  ${ARGV2}")
  endif()
endfunction()

set(Name Charlie)
print_detail5(Name Bob)
# My name is Charlie
# Hello, my name is Bob