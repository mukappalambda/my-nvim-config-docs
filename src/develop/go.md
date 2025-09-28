# Setup Go Development Environment

The followings are the recommended tools to set up:

- `delve`
- `golangci-lint`

---

## `delve`

Installing [delve](https://github.com/go-delve/delve):

```bash
go install github.com/go-delve/delve/cmd/dlv@latest
```

Navigate [here](https://github.com/go-delve/delve/tree/master/Documentation/installation) to see more details.

---

## `golangci-lint`

Two methods shown here to install [golangci-lint](https://github.com/golangci/golangci-lint):

- Using the official script
- Using [mise](https://github.com/jdx/mise)

Installing `golangci-lint` using the official script:

**Using the official script**

_Use pre-built binary (Recommended)_

```bash
curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/HEAD/install.sh | sh -s -- -b $(go env GOPATH)/bin v2.5.0
```

_Use go toolchain (aren’t guaranteed to work)_

```bash
go install github.com/golangci/golangci-lint/v2/cmd/golangci-lint@v2.5.0
```

Reference: [golangci-lint documentation](https://golangci-lint.run/docs/welcome/install/)

**Using `mise`**

```bash
mise use golangci-lint -g
```
