load("@build_bazel_rules_apple//apple:ios.bzl", "ios_unit_test")
load("@build_bazel_rules_apple//apple:resources.bzl", "apple_precompiled_resource_bundle")
load("@build_bazel_rules_swift//swift:swift_library.bzl", "swift_library")


apple_precompiled_resource_bundle(
    name = "MyAppLibBundle",
    infoplists = glob(["ResourceBundle_Info.plist"]),
    resources = glob(["Resources/**/*"]),
)

swift_library(
    name = "MyAppLib",
    srcs = glob(["**/*.swift"]),
    data = [":MyAppLibBundle"],
)

swift_library(
    name = "MyAppLibTestsLib",
    srcs = glob(["Tests/**/*.swift"]),
    deps = [":MyAppLib"],
)

ios_unit_test(
    name = "MyAppLibTests",
    bundle_name = "MyAppLibTests",
    minimum_os_version = "16.0",
    deps = [":MyAppLibTestsLib"],
)