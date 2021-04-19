cmake_minimum_required(VERSION 3.0.0)

set(NAME Alice)

set(Alice Bob)

message(${${NAME}}) # Bob

message(NAME ${NAME} ${${NAME}}) # NAMEAliceBob

message(NAME${NAME}${${NAME}}) # NAMEAliceBob

message("NAME ${NAME} ${${NAME}}") # NAME Alice Bob

set(NAMEAliceBob Charlie)

message(${NAME${NAME}${${NAME}}}) # Charlie

# message(${NAME ${NAME} ${${NAME}}}) # Error!