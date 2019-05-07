cmake_minimum_required(VERSION 3.9)
project(impressionist)

# Standard UPS/Cetbuildtools stanza (cargo-culted from cetlib)
find_package(cetbuildtools 7 REQUIRED)
include(CetCMakeEnv)
cet_cmake_env()
cet_set_compiler_flags(
  DIAGS VIGILANT WERROR NO_UNDEFINED
  EXTRA_FLAGS -pedantic
  EXTRA_CXX_FLAGS -Wnon-virtual-dtor -Wdelete-non-virtual-dtor
  )

# Ignore CET_SANITIZE... for now

# Sanity check
add_executable(cbt-sanity smoketest/sanity.cc)

# FHiCL
add_subdirectory(fcl)
