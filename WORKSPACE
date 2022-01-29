workspace(
    name = "bazel-monorepo-sample",
    managed_directories = {
        "@npm_bff_graphql": ["./bff/services/graphql/node_modules"],
        "@npm_frontend_ui": ["./frontend/apps/ui/node_modules"],
    },
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# JS
http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "d63ecec7192394f5cc4ad95a115f8a6c9de55c60d56c1f08da79c306355e4654",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/4.6.1/rules_nodejs-4.6.1.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "yarn_install")

node_repositories(
    node_version = "16.13.2",
)

yarn_install(
    name = "npm_bff_graphql",
    package_json = "//bff/services/graphql:package.json",
    yarn_lock = "//bff/services/graphql:yarn.lock",
)

yarn_install(
    name = "npm_frontend_ui",
    package_json = "//frontend/apps/ui:package.json",
    yarn_lock = "//frontend/apps/ui:yarn.lock",
)

