# -*- python -*-

load("//tools:install.bzl", "cmake_config", "install", "install_cmake_config")

package(default_visibility = ["//visibility:public"])

CMAKE_PACKAGE = "optitrack"

cmake_config(
    cps_file_name = CMAKE_PACKAGE + ".cps",
    package = CMAKE_PACKAGE,
)

install_cmake_config(
    package = CMAKE_PACKAGE,
    versioned = 0,
)

OPTITRACK_TARGETS = [
    "@optitrack_driver//lcmtypes:lcmtypes_optitrack",
    "@optitrack_driver//lcmtypes:optitrack_lcmtypes",
    "@optitrack_driver//lcmtypes:py_optitrack_lcmtypes",
    "@optitrack_driver//src:optitrack_client",
]

install(
    name = "install",
    allowed_externals = OPTITRACK_TARGETS,
    doc_dest = "share/doc/" + CMAKE_PACKAGE,
    doc_strip_prefix = ["**/"],
    guess_hdrs = "PACKAGE",
    hdr_dest = "include/lcmtypes",
    license_docs = ["@optitrack_driver//:LICENSE"],
    java_strip_prefix = ["**/"],
    py_dest = "lib/python2.7/site-packages/optitrack",
    py_strip_prefix = ["**/"],
    targets = OPTITRACK_TARGETS,
    deps = [":install_cmake_config"],
    visibility = ["//:__pkg__"],
)
