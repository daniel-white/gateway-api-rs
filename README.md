[![Docs](https://img.shields.io/badge/docs-docs.rs-ff69b4.svg)](https://docs.rs/gateway-api/)
[![crates.io](https://img.shields.io/crates/v/gateway-api.svg)](https://crates.io/crates/gateway-api)
[![License](https://img.shields.io/badge/license-mit-blue.svg)](https://raw.githubusercontent.com/kube-rs/gateway-api-rs/main/LICENSE)

> **Warning**: EXPERIMENTAL. **Not ready for production use**.

> **Note**: This library should be considered "unofficial". While the aspiration
> is to eventually become the "official" Gateway API bindings for Rust,
> [Kubernetes SIG Network] has not yet (and may never) officially endorsed it.

[Kubernetes SIG Network]:https://github.com/kubernetes/community/tree/master/sig-network

# Gateway API (Rust)

> **Note**: Currently supports [Gateway API version v1.2.1][gwv]

This project provides bindings in [Rust] for [Kubernetes] [Gateway API].

[gwv]:https://github.com/kubernetes-sigs/gateway-api/releases/tag/v1.2.1
[Rust]:https://rust-lang.org
[Kubernetes]:https://kubernetes.io/
[Gateway API]:https://gateway-api.sigs.k8s.io/

## Usage

Basic usage involves using a [kube-rs] [Client] to perform create, read, update
and delete (CRUD) operations on [Gateway API resources]. You can either use a
basic `Client` to perform CRUD operations, or you can build a [Controller]. See
the `gateway-api/examples/` directory for detailed (and specific) usage examples.

[kube-rs]:https://github.com/kube-rs/kube
[Gateway API resources]:https://gateway-api.sigs.k8s.io/api-types/gateway/
[Client]:https://docs.rs/kube/latest/kube/struct.Client.html
[Controller]:https://kube.rs/controllers/intro/

## Development

This project uses [Kopium] to automatically generate API bindings from upstream
Gateway API. Make sure you install `kopium` locally in order to run the
generator:

```console
$ cargo install kopium
```

After which you can run the `update.sh` script:

```console
$ ./update.sh
```

Check for errors and/or a non-zero exit code, but upon success you should see
updates automatically generated for code in the `gateway-api/src/api` directory
which you can then commit.

[Kopium]:https://github.com/kube-rs/kopium
