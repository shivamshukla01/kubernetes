load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "checkpoint.go",
        "state.go",
        "state_checkpoint.go",
        "state_mem.go",
    ],
    importpath = "k8s.io/kubernetes/pkg/kubelet/cm/memorymanager/state",
    visibility = ["//visibility:public"],
    deps = [
        "//pkg/kubelet/checkpointmanager:go_default_library",
        "//pkg/kubelet/checkpointmanager/checksum:go_default_library",
        "//pkg/kubelet/checkpointmanager/errors:go_default_library",
        "//staging/src/k8s.io/api/core/v1:go_default_library",
        "//vendor/k8s.io/klog/v2:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = ["state_checkpoint_test.go"],
    embed = [":go_default_library"],
    deps = [
        "//pkg/kubelet/checkpointmanager:go_default_library",
        "//pkg/kubelet/cm/cpumanager/state/testing:go_default_library",
        "//staging/src/k8s.io/api/core/v1:go_default_library",
        "//vendor/github.com/stretchr/testify/assert:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
