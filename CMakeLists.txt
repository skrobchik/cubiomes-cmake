cmake_minimum_required(VERSION 3.26)

project(cubiomes)

add_library(libcubiomes
    biomenoise.c biomenoise.h
    biomes.h
    biometree.c
    finders.c finders.h
    generator.c generator.h
    layers.c layers.h
    noise.c noise.h
    quadbase.c quadbase.h
    rng.h
    util.c util.h
)
target_include_directories(libcubiomes PUBLIC
    biomenoise.h
    biomes.h
    finders.h
    generator.h
    layers.h
    noise.h
    quadbase.h
    rng.h
    util.h
)

add_executable(cubiomes_tests tests.c)
target_link_libraries(cubiomes_tests libcubiomes)
