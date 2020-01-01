load("@rules_cc//cc:defs.bzl", "cc_library")

cc_library(
    name = "rplidar_driver",
    srcs = ["src/rplidar_driver.cpp"],
    hdrs = glob(["**/*.h"]),
    includes = ["include", "src"],
    visibility = ["//visibility:public"],
)
