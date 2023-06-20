# Architecture Guidelines

The guide below describes guidelines applicable to repository.

## MACH Architecture

Overall this repository adheres to a Microservices-based, API-first,
Cloud-native, and Headless architecture.

## Infrastructure as a Service

AWS was selected a single IaaS provider. This project assumes it will fail
before AWS does. Vendor lock-in/buy-in allows leveraging numerous
undifferentiated services. For this project that outweighs being cloud agnostic.

## Monorepo

The project is designed as a monorepo instead of polyrepo. Apps will be mostly
serverless microservices and a monorepo is believed to help streamline changes.

## Monorepo Manager

Microsoft backed Rush was selected over Nx, Lerna, Turbo, etc. for monorepo
management.

## Typescript

Javascript was selected as a base language for microservices due to its
performance and omnipresence. Microsoft backed Typescript compiling is used for
Javascript. Typescript offers typehinting, easies in maintenance, and code
readability.

## File Structure

Parent project folder structure mimics that of Microsoft Rushstack. As for
individual package files, generally files that change together should stay
together. Structure code by feature.

## Package Manager

PNPM was selected for as the Javascript package manager over Yarn and NPM. Yarn
workspaces are not supported in Rush, which would be the primary motivation
behind using Yarn. Microsoft purchased NPM, but it remains infamous. PNPM uses
symlinks which helps minimize dependency storage.

## Heft

Rush Heft was selected to build Typescript projects mainly because it
accompanies Rush. Heft Node Rig was selected as many projects will have same
configuration.

## AWS CDK

AWS CDK was selected instead of
[Serverless Framework](https://github.com/serverless-stack/serverless-stack).
When it comes down to it, SST is an unnecessary and incomplete abstraction
layer. SST live lambda development works using serverless website. There does
not appear to be a need to add a reliance on SST. SST future plans, incentives,
and kickback are questionable.

## AWS SSO

AWS SSO was selected for authentication over hard coded credentials for easy of
maintenance and security.

## Documentation

Documentation as code is desired. Documentation should be maintained where it
will be looked for. Tsdoc was selected as a standard for writing Typescript
documentation. Typedoc was selected to compile documentation as code.

## Deployments

`rush deploy` is used in CI only to copy services and dependencies into
deployable compressed file. Each compressed file is uploaded to S3 for AWS
CodePipeline.

Each app is capable of deployment themselves using CDK via `rushx cdk:deploy`.
