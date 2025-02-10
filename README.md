<p align="center">
  <img src="https://user-images.githubusercontent.com/1370944/109153827-15c4d700-7776-11eb-93c0-6801f8d618b0.jpg"
    alt="Vault12 Recovery Utility">
</p>

<p align="center">
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-blue.svg" alt="MIT License" />
  </a>
  <img src="https://img.shields.io/david/vault12/recovery-utility" alt="Dependencies" />
  <a href="http://makeapullrequest.com">
    <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs welcome" />
  </a>
  <a href="https://twitter.com/_Vault12_">
    <img src="https://img.shields.io/twitter/follow/_Vault12_?label=Follow&style=social" alt="Follow" />
  </a>
</p>

# Overview

A command-line utility for recovering assets from the raw data exported from [Vault12 mobile app](https://vault12.com/download/).

## Installation

1. Install [node](https://nodejs.org/)
2. Install the package globally:
```
$ npm i -g vault12-recovery
```
## Usage

1. Export the decryption key (`vault12.json`) from the Vault12 app: *Settings > Advanced > Export My Vault’s Decryption Key*.
2. Collect the raw Vault data from several Guardian devices via *Settings > Advanced > Export Data for External Vault*. You'll need to collect the amount of files equal to the **Number of Confirmations** you selected when creating the Vault.
3. Place all exported archives and `vault12.json` file in the same directory, e.g. `~/vault12-files`.
4. In terminal, run
```
$ vault12-recovery ~/vault12-files
```
5. You should find all recovered assets from the Vault in the directory `~/vault12-files/output`.

## Validation

The utility includes several validation functions to ensure the integrity of the data:

1. `validateVaultData`: Validates the structure of the `vault12.json` file.
2. `validateZipArchives`: Validates the structure of the zip archives.
3. `validateAssetShards`: Validates the structure of the asset shards.

These validation steps are automatically performed during the recovery process to ensure the data is correctly structured and can be successfully decrypted.

## Total Allowance

The utility calculates the total allowance of assets during the recovery process. The total allowance is the sum of the sizes of all assets in the vault. This value is displayed at the end of the recovery process.
