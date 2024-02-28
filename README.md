# MORPHEUS NODE

## Setup & Installation

Clone the repo and in the root run:
- `yarn` - to install packages and setup, this should take care of everything needed to be able to run locally

## Local Development

To start the local development node, run:
- `yarn start`

## Packaging and making distributable format

### Platform specific bundle

To create a platform-specific executable bundle, run:
- `yarn run package` - this will create a package for local platform

To create a package for a different platform, run:
- `yarn run package --platform={desiredPlatform}` where desiredPlatform: `darwin`, `win` or `linux`

or different architecture:
- `yarn run package --arch={desiredArch}` where desiredArch: `ia32`, `x64`, `armv7l`, `arm64`, `universal` or `mips64el`

### Proper distributable format

To create a proper platform distributable, run:
- `yarn run make` - this will create a distributable for local platform

For different platforms, use the same parameters as in the Platform specific bundle

Please visit MOR.software to sign up as a developer to be rewarded for your merged contributions.  Submit an MRC to get support for feature and improvement ideas.

MOR.software is also the place to build, submit, deplloy, and manage all of your Smart Agents.
