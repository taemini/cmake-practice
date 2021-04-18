# cmake-practice

## build commands

- section1/1-no-header-files
- section1/2-with-header-files

  ```bash
  g++ main.cpp addition.cpp division.cpp print_result.cpp -o calculator
  ./calculator
  ```

- section1/3-glimpse-of-makefile

  ```bash
  make
  ./calculator
  ```

- section2/1-cmake-getting-started
- section2/2-cmake-managing-hierarchy

  ```bash
  cd my_build_dir
  cmake ..
  make
  ./calculator
  ```

- section3/1-organize-with-subdirectory
  ```bash
  cd build
  cmake ..
  make
  ./calculator
  ```
