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
    hdrs = glob(["\include\*.h"]) + select({
        "@bazel_tools//src/conditions:windows": glob(["src/arch/win32/*.hpp"]),
        "//conditions:default": glob(["src/arch/linux/*.hpp"]),
    }) + glob(["src/*.h"]),
    includes = [
        "include",
        "src",
    ],
    visibility = ["//visibility:public"],
)
