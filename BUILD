package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_go//go:def.bzl", "go_binary")
load("@io_bazel_rules_docker//go:image.bzl", "go_image", GO_DEFAULT_BASE="DEFAULT_BASE")
load("@io_bazel_rules_docker//container:container.bzl", "container_image", "container_push")

go_binary(
    name = "server",
    srcs = ["main.go"],
)

go_image(
    name = "server_image_runnable",
    binary = ":server",
)

container_image(
    name = "go_base_image",
    base = GO_DEFAULT_BASE,
    ports = ["8181"]
)

go_image(
    name = "server_image_not_runnable",
    binary = ":server",
    base = ":go_base_image",
)
