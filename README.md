To reproduce the issue run `bazel test //MyApp:MyAppLibTests`


Output:
```
lucasmarcal@lucas-marcal-M37P4T7PNR example-proj-apple-precompiled % bazelisk test //MyApp:MyAppLibTests
ERROR: /Users/lucasmarcal/Development/example-proj-apple-precompiled/MyApp/BUILD:24:14: in _ios_internal_unit_test_bundle rule //MyApp:MyAppLibTests.__internal__.__test_bundle: 
Traceback (most recent call last):
        File "/private/var/tmp/_bazel_lucasmarcal/a15d8f00f3f321377792ffdc3a5c3373/external/rules_apple~/apple/internal/testing/ios_rules.bzl", line 77, column 60, in _ios_unit_test_bundle_impl
                return apple_test_bundle_support.apple_test_bundle_impl(
        File "/private/var/tmp/_bazel_lucasmarcal/a15d8f00f3f321377792ffdc3a5c3373/external/rules_apple~/apple/internal/testing/apple_test_bundle_support.bzl", line 526, column 41, in _apple_test_bundle_impl
                processor_result = processor.process(
        File "/private/var/tmp/_bazel_lucasmarcal/a15d8f00f3f321377792ffdc3a5c3373/external/rules_apple~/apple/internal/processor.bzl", line 747, column 36, in _process
                partial_outputs = [partial.call(p) for p in partials]
        File "/private/var/tmp/_bazel_lucasmarcal/a15d8f00f3f321377792ffdc3a5c3373/external/bazel_skylib~/lib/partial.bzl", line 43, column 28, in _call
                return partial.function(*function_args, **function_kwargs)
        File "/private/var/tmp/_bazel_lucasmarcal/a15d8f00f3f321377792ffdc3a5c3373/external/rules_apple~/apple/internal/partials/resources.bzl", line 299, column 26, in _resources_partial_impl
                resources.deduplicate(
        File "/private/var/tmp/_bazel_lucasmarcal/a15d8f00f3f321377792ffdc3a5c3373/external/rules_apple~/apple/internal/resources.bzl", line 981, column 42, in _deduplicate
                deduplicated = _deduplicate_field(
        File "/private/var/tmp/_bazel_lucasmarcal/a15d8f00f3f321377792ffdc3a5c3373/external/rules_apple~/apple/internal/resources.bzl", line 926, column 49, in _deduplicate_field
                path_origins = processed_origins[short_path]
Error: key "MyApp/MyAppLibBundle-intermediates/storyboards/MyAppLibBundle.bundle/Base.lproj/MyAppLibBundle" not found in dictionary
ERROR: /Users/lucasmarcal/Development/example-proj-apple-precompiled/MyApp/BUILD:24:14: Analysis of target '//MyApp:MyAppLibTests.__internal__.__test_bundle' failed
ERROR: Analysis of target '//MyApp:MyAppLibTests' failed; build aborted: Analysis failed
```
