load("@rules_cc//cc:defs.bzl", "cc_library")

cc_library(
    name = "rplidar_driver",
    srcs = [
        "src/rplidar_driver.cpp",
        "src/hal/thread.cpp",
    ] + select({
        "@bazel_tools//src/conditions:windows": glob(["src/arch/win32/*.cpp"]),
        "//conditions:default": glob(["src/arch/linux/*.cpp"]),
    }),
    hdrs = glob([r"include/*.h"]) + select({
        "@bazel_tools//src/conditions:windows": glob(["src/arch/win32/*.hpp"]) + glob(["src/arch/win32/*.h"]),
        "//conditions:default": glob(["src/arch/linux/*.hpp"]) + glob(["src/arch/linux/*.h"]),
    }) + glob([r"src/*.h", r"src/hal/*.h"]),
    includes = [
        "include",
        "src",
    ],
    visibility = ["//visibility:public"],
)
