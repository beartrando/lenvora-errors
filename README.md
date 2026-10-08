# @shared/errors

Shared error types for Lenvora services. Implements the `common.error` proto contract.

## Usage

```ts
import { NotFoundError } from "@shared/errors";
```

## Proto codegen

`src/contracts/proto/common/error.ts` is generated from the [lenvora-proto](https://github.com/beartrando/lenvora-proto)
repository and **committed** (it is required to build the package). To regenerate after a contract change, clone the
proto repository next to this one:

```bash
git clone git@github.com:beartrando/lenvora-proto.git ../proto
pnpm install
pnpm proto:generate
```

If the proto repository lives elsewhere, point to it explicitly: `PROTO_DIR=/path/to/proto pnpm proto:generate`.

## Development

```bash
pnpm install
pnpm dev    # tsc -w
pnpm build  # tsc -p tsconfig.json
```

## Release

1. Commit changes.
2. Bump `version` in `package.json` (semver).
3. Tag and push: `git tag v1.0.0 && git push --tags`.
4. Update consumers (`services/*/package.json`) to the new tag: `git+https://github.com/beartrando/errors.git#v1.0.0`.
