# The Istio API definitions provided by Alibabacloud Service Mesh (ASM)

This repository is the Istio API definitions provided by Alibabacloud Service Mesh (ASM), which is compatible with [istio/api](https://github.com/istio/api).

Below is derived from istio community README.

# Istio APIs and Common Configuration Definitions

This repository defines component-level APIs and common configuration formats for the Istio
platform. These definitions are specified using the [protobuf](https://github.com/google/protobuf)
syntax.

This repository depends only on the [tools](https://github.com/istio/tools) repository for tools used during build. This repository *will not* depend on any
other repositories. Except for tools, all other Istio repositories can take a dependency on the api repository.

## API Guidelines

When making changes to the protos in this repository, your changes **must** comply with the [API guidelines](./GUIDELINES.md).

## Updating

After the [protobuf](https://github.com/google/protobuf) definitions
are updated, the corresponding `*pb.go`, `_pb2.py`, `*.json` and
Kubernetes Custom Resource Definition files must be
generated by running `make gen` and submitted as
part of the same PR as the updated definitions. Also `make
proto-commit` must be run to update the proto.lock file with new
changes.

## Backwards Incompatible Changes

If a PR tries to make backwards incompatible changes, it will be
blocked by protolock. To force these changes in, install
[protolock](https://github.com/nilslice/protolock) and run
`protolock commit --force`.

You must include a note in your PR that you had to force the
protolock and why.
