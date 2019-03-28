workspace(name = "bazeldockerrunnable")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Rules for Go - https://github.com/bazelbuild/rules_go
http_archive(
    name = "io_bazel_rules_go",
    urls = ["https://github.com/bazelbuild/rules_go/releases/download/0.18.1/rules_go-0.18.1.tar.gz"],
    sha256 = "77dfd303492f2634de7a660445ee2d3de2960cbd52f97d8c0dffa9362d3ddef9",
)
load("@io_bazel_rules_go//go:deps.bzl", "go_rules_dependencies", "go_register_toolchains")
go_rules_dependencies()
go_register_toolchains()

# Docker rules for Go - https://github.com/bazelbuild/rules_docker#go_image

http_archive(
    name = "io_bazel_rules_docker",
    strip_prefix = "rules_docker-e11f49d454e873718681f0af4cdc89e94ce13d6f",
    urls = ["https://github.com/bazelbuild/rules_docker/archive/e11f49d454e873718681f0af4cdc89e94ce13d6f.tar.gz"],
)
load(
    "@io_bazel_rules_docker//go:image.bzl",
    _go_image_repos = "repositories",
)
_go_image_repos()
