<!-- Template: copy to your project or place a copy at projects/<name>/threat_model.md. Free text; the scanner reads it before it starts. -->
# Threat model

## What this project does and where untrusted input enters

This project provides a webapp written on Python that is deployed on Heroku. It is used by the conda-forge to orchestrate different infrastructure components: gating packages uploads to only allowed repositories, responding to special commands issued by mentioning `@conda-forge-admin` on comments, issue titles and PRs, and other tasks.

## Components that matter most / least

Many of these operations need a token with privileged access to production resources. Be extra careful with those.

## How to exercise it

The `.github/workflows/tests.yml` workflow contains logic to build the Docker image and run the tests. Live tests need special tokens not publicly available, skip those.

## How you rate severity

- Unauthorized uploads would be pretty severe
- Using the tokens to perform write operations would be severe
- DoS attacks would prevent conda-forge from operating normally, treat it as high

## Anything to leave alone

Nothing to highlight.
