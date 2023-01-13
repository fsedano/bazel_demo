load("@io_bazel_rules_docker//python3:image.bzl", "py3_image")
load("@io_bazel_rules_docker//container:container.bzl", "container_push")

py3_image(
    name = "hello",
    srcs = ["hello.py"],
    main = "hello.py",
)

container_push(
    name = "hello-push",
    image = ":hello",
    registry = "docker.io",
    repository = "fsedano/test1",
    format = "OCI",
    tag = "{STABLE_GIT_SHA}",
    skip_unchanged_digest = True
)