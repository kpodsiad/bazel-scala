load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary", "scala_library")
scala_binary(
    name = "App",
    srcs = glob(["src/main/scala/me/kpodsiad/*.scala"]),
    main_class = "me.kpodsiad.Main",
    scalacopts = ["-Xplugin:./semanticdb-scalac_2.13.3-4.4.29.jar", "-Yrangepos", "-P:semanticdb:targetroot:src/target"]
)

load("@io_bazel_rules_scala//scala:scala_toolchain.bzl", "scala_toolchain")

scala_toolchain(
    name = "diagnostics_reporter_toolchain_impl",
    enable_diagnostics_report = True,
    visibility = ["//visibility:public"],
)

toolchain(
    name = "diagnostics_reporter_toolchain",
    toolchain = "diagnostics_reporter_toolchain_impl",
    toolchain_type = "@io_bazel_rules_scala//scala:toolchain_type",
    visibility = ["//visibility:public"],
)

