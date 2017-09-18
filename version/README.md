# Tendermint Version

## SemVer

Tendermint uses [SemVer](http://semver.org/) to determine when and how the version changes.
According to SemVer, anything in the public API can change at any time before version 1.0.0

To provide some stability to Tendermint users in these 0.X.X days, the MINOR version is used
to signal breaking changes across a subset of the total public API. This subset includes all
interfaces exposed to other processes (cli, rpc, p2p, etc.), as well as parts of the following packages:

- types
- rpc/client
- config
- node

Exported objects in these packages that are not covered by the versioning scheme 
are explicitly marked by `// UNSTABLE` in their go doc comment and may change at any time.
Functions, types, and values in any other package may also change at any time.

## Upgrades

In an effort to avoid accumulating technical debt prior to 1.0.0,
we do not guarantee that breaking changes (ie. bumps in the MINOR version)
will work with existing tendermint blockchains. In these cases you will
have to start a new blockchain, or write something custom to get the old
data into the new chain.

However, any bump in the PATCH version should be compatible with existing histories
(if not please open an [issue](https://github.com/tendermint/tendermint/issues)).
