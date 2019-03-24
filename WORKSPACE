workspace(name = "jupyter_bazel")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
git_repository(
    name = "io_bazel_rules_python",
    commit = "965d4b4a63e6462204ae671d7c3f02b25da37941",
    remote = "https://github.com/bazelbuild/rules_python.git",
)

# Only needed for PIP support:
load("@io_bazel_rules_python//python:pip.bzl", "pip_repositories")
load("@io_bazel_rules_python//python:pip.bzl", "pip_import")

# Requirements for notebooks
pip_import(
    name = "notebooks",
    requirements = "//notebooks:requirements.txt",
)

load(
    "@notebooks//:requirements.bzl",
    _notebooks_install = "pip_install",
)
_notebooks_install()

