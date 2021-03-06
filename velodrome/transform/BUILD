package(default_visibility = ["//visibility:public"])

licenses(["notice"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_binary",
    "go_library",
    "go_test",
)

go_binary(
    name = "transform",
    library = ":go_default_library",
    tags = ["automanaged"],
)

go_test(
    name = "go_default_test",
    srcs = [
        "fetcher_test.go",
        "influx_test.go",
    ],
    library = ":go_default_library",
    tags = ["automanaged"],
    deps = [
        "//velodrome/sql:go_default_library",
        "//velodrome/sql/testing:go_default_library",
    ],
)

go_library(
    name = "go_default_library",
    srcs = [
        "fetcher.go",
        "influx.go",
        "transform.go",
    ],
    tags = ["automanaged"],
    deps = [
        "//velodrome/sql:go_default_library",
        "//velodrome/transform/plugins:go_default_library",
        "//vendor:github.com/golang/glog",
        "//vendor:github.com/influxdata/influxdb/client/v2",
        "//vendor:github.com/jinzhu/gorm",
        "//vendor:github.com/jinzhu/gorm/dialects/mysql",
        "//vendor:github.com/spf13/cobra",
    ],
)

filegroup(
    name = "configs",
    srcs = glob(["*.yaml"]),
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [
        ":package-srcs",
        "//velodrome/transform/plugins:all-srcs",
    ],
    tags = ["automanaged"],
)
