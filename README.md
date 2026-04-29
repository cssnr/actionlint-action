[![GitHub Tag Major](https://img.shields.io/github/v/tag/cssnr/actionlint-action?sort=semver&filter=!v*.*&logo=git&logoColor=white&labelColor=585858&label=%20)](https://github.com/cssnr/actionlint-action/tags)
[![GitHub Tag Minor](https://img.shields.io/github/v/tag/cssnr/actionlint-action?sort=semver&filter=!v*.*.*&logo=git&logoColor=white&labelColor=585858&label=%20)](https://github.com/cssnr/actionlint-action/releases)
[![GitHub Release Version](https://img.shields.io/github/v/release/cssnr/actionlint-action?logo=git&logoColor=white&labelColor=585858&label=%20)](https://github.com/cssnr/actionlint-action/releases/latest)
[![Action Run Using](https://img.shields.io/badge/dynamic/yaml?url=https%3A%2F%2Fraw.githubusercontent.com%2Fcssnr%2Factionlint-action%2Frefs%2Fheads%2Fmaster%2Faction.yml&query=%24.runs.using&logo=githubactions&logoColor=white&label=runs)](https://github.com/cssnr/actionlint-action/blob/master/action.yml)
[![Workflow Release](https://img.shields.io/github/actions/workflow/status/cssnr/actionlint-action/release.yaml?logo=norton&logoColor=white&label=release)](https://github.com/cssnr/actionlint-action/actions/workflows/release.yaml)
[![Workflow Lint](https://img.shields.io/github/actions/workflow/status/cssnr/actionlint-action/lint.yaml?logo=norton&logoColor=white&label=lint)](https://github.com/cssnr/actionlint-action/actions/workflows/lint.yaml)
[![GitHub Last Commit](https://img.shields.io/github/last-commit/cssnr/actionlint-action?logo=github&label=updated)](https://github.com/cssnr/actionlint-action)
[![Codeberg Last Commit](https://img.shields.io/gitea/last-commit/cssnr/actionlint-action/master?gitea_url=https%3A%2F%2Fcodeberg.org%2F&logo=codeberg&logoColor=white&label=updated)](https://codeberg.org/cssnr/actionlint-action)
[![GitHub Repo Size](https://img.shields.io/github/repo-size/cssnr/actionlint-action?logo=buffer&label=repo%20size)](https://github.com/cssnr/actionlint-action?tab=readme-ov-file#readme)
[![GitHub Contributors](https://img.shields.io/github/contributors-anon/cssnr/actionlint-action?logo=southwestairlines)](https://github.com/cssnr/actionlint-action/graphs/contributors)
[![GitHub Issues](https://img.shields.io/github/issues/cssnr/actionlint-action?logo=codeforces&logoColor=white)](https://github.com/cssnr/actionlint-action/issues)
[![GitHub Discussions](https://img.shields.io/github/discussions/cssnr/actionlint-action?logo=livechat&logoColor=white)](https://github.com/cssnr/actionlint-action/discussions)
[![GitHub Forks](https://img.shields.io/github/forks/cssnr/actionlint-action?style=flat&logo=forgejo&logoColor=white)](https://github.com/cssnr/actionlint-action/forks)
[![GitHub Repo Stars](https://img.shields.io/github/stars/cssnr/actionlint-action?style=flat&logo=gleam&logoColor=white)](https://github.com/cssnr/actionlint-action/stargazers)
[![GitHub Org Stars](https://img.shields.io/github/stars/cssnr?style=flat&logo=apachespark&logoColor=white&label=org%20stars)](https://cssnr.github.io/)
[![Discord](https://img.shields.io/discord/899171661457293343?logo=discord&logoColor=white&label=discord&color=7289da)](https://discord.gg/wXy6m2X8wY)
[![Ko-fi](https://img.shields.io/badge/Ko--fi-72a5f2?logo=kofi&label=support)](https://ko-fi.com/cssnr)

# Actionlint Action

- [Inputs](#Inputs)
- [Outputs](#Outputs)
- [Tags](#Tags)
- [Support](#Support)
- [Contributing](#Contributing)

Easily use [rhysd/actionlint](https://github.com/rhysd/actionlint) in a Workflow run with Pyflakes and Actions caching.

Supports and tested on Linux, Windows and macOS on both Intel and ARM architectures.

[![Linux](https://img.shields.io/badge/linux-orange?style=for-the-badge&logo=linux&logoColor=white)](https://github.com/cssnr/actionlint-action/actions/workflows/test.yaml)
[![Windows](https://img.shields.io/badge/windows-blue?style=for-the-badge&logo=gitforwindows&logoColor=white)](https://github.com/cssnr/actionlint-action/actions/workflows/test.yaml)
[![macOS](https://img.shields.io/badge/macos-black?style=for-the-badge&logo=apple&logoColor=white)](https://github.com/cssnr/actionlint-action/actions/workflows/test.yaml)

```yaml
- name: 'Actionlint'
  uses: cssnr/actionlint-action@master
```

By default, this downloads the latest version of actionlint and stores it in Actions cache for future runs.
Allows setting a specific version of actionlint, setting custom command-line arguments and ShellCheck options.
Automatically detect Architecture for matrix runs or specify an [architecture](#arch).

## Inputs

| Input                               | Default&nbsp;Value | Description&nbsp;of&nbsp;the&nbsp;Input&nbsp;Value |
| :---------------------------------- | :----------------: | :------------------------------------------------- |
| [version](#version)                 |      `latest`      | Actionlint Version Tag                             |
| [arguments](#arguments)             |         -          | Command Line Arguments                             |
| [shellcheck_opts](#shellcheck_opts) |         -          | SHELLCHECK_OPTS                                    |
| [arch](#arch)                       |         -          | Architecture String                                |
| [pyflakes](#pyflakes)               |       `true`       | Install Pyflakes                                   |
| token                               |   `github.token`   | Custom GitHub PAT                                  |

#### version

This must be a Version **TAG** from an actionlint [release](https://github.com/rhysd/actionlint/releases)

Example: `v1.7.9`  
Default: `latest`

#### arguments

Command line arguments.

```shell
actionlint -color -verbose ${{ inputs.arguments }}
```

#### shellcheck_opts

To ignore specific errors. [ShellCheck Wiki](https://github.com/koalaman/shellcheck/wiki/Ignore#ignoring-errors-in-one-specific-run).

Example: `-e SC2059 -e SC2034`

#### arch

The script attempts to automatically detect the architecture.

Should this fail you can set one of these:

```text
darwin_amd64
darwin_arm64
freebsd_386
freebsd_amd64
linux_386
linux_amd64
linux_arm64
linux_armv6
```

For more details see the actionlint [release assets](https://github.com/rhysd/actionlint/releases).

#### pyflakes

Install Pyflakes and store in cache for future runs.

## Outputs

[Let us know](#Support) if you need any outputs...

## Tags

The following rolling [tags](https://github.com/cssnr/actionlint-action/tags) are maintained.

| Version&nbsp;Tag                                                                                                                                                                                                   | Rolling | Bugs | Feat. |   Name    |  Target  | Example  |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :-----: | :--: | :---: | :-------: | :------: | :------- |
| [![GitHub Tag Major](https://img.shields.io/github/v/tag/cssnr/actionlint-action?sort=semver&filter=!v*.*&style=for-the-badge&label=%20&color=44cc10)](https://github.com/cssnr/actionlint-action/releases/latest) |   ✅    |  ✅  |  ✅   | **Major** | `vN.x.x` | `vN`     |
| [![GitHub Tag Minor](https://img.shields.io/github/v/tag/cssnr/actionlint-action?sort=semver&filter=!v*.*.*&style=for-the-badge&label=%20&color=blue)](https://github.com/cssnr/actionlint-action/releases/latest) |   ✅    |  ✅  |  ❌   | **Minor** | `vN.N.x` | `vN.N`   |
| [![GitHub Release](https://img.shields.io/github/v/release/cssnr/actionlint-action?style=for-the-badge&label=%20&color=red)](https://github.com/cssnr/actionlint-action/releases/latest)                           |   ❌    |  ❌  |  ❌   | **Micro** | `vN.N.N` | `vN.N.N` |

You can view the release notes for each version on the [releases](https://github.com/cssnr/actionlint-action/releases) page.

The **Major** tag is recommended. It is the most up-to-date and always backwards compatible.
Breaking changes would result in a **Major** version bump. At a minimum you should use a **Minor** tag.

# Support

If you run into any issues or need help getting started, please do one of the following:

- [Report an Issue](https://github.com/cssnr/actionlint-action/issues)
- [Q&A Discussion](https://github.com/cssnr/actionlint-action/discussions/categories/q-a)
- [Request a Feature](https://github.com/cssnr/actionlint-action/issues/new?template=1-feature.yaml)
- [Chat with us on Discord](https://discord.gg/wXy6m2X8wY)

[![Features](https://img.shields.io/badge/features-brightgreen?style=for-the-badge&logo=rocket&logoColor=white)](https://github.com/cssnr/actionlint-action/issues/new?template=1-feature.yaml)
[![Issues](https://img.shields.io/badge/issues-red?style=for-the-badge&logo=southwestairlines&logoColor=white)](https://github.com/cssnr/actionlint-action/issues)
[![Discussions](https://img.shields.io/badge/discussions-blue?style=for-the-badge&logo=livechat&logoColor=white)](https://github.com/cssnr/actionlint-action/discussions)
[![Discord](https://img.shields.io/badge/discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/wXy6m2X8wY)

# Contributing

If you would like to submit a PR, please review the [CONTRIBUTING.md](#contributing-ov-file).

Please consider making a donation to support the development of this project
and [additional](https://cssnr.com/) open source projects.

[![Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/cssnr)

[![Actions Tools](https://raw.githubusercontent.com/smashedr/repo-images/refs/heads/master/actions/actions-tools.png)](https://actions-tools.cssnr.com/)

Additionally, you can support other [GitHub Actions](https://actions.cssnr.com/) I have published:

- [Stack Deploy Action](https://github.com/cssnr/stack-deploy-action?tab=readme-ov-file#readme)
- [Portainer Stack Deploy Action](https://github.com/cssnr/portainer-stack-deploy-action?tab=readme-ov-file#readme)
- [Docker Context Action](https://github.com/cssnr/docker-context-action?tab=readme-ov-file#readme)
- [Actions Up Action](https://github.com/cssnr/actions-up-action?tab=readme-ov-file#readme)
- [Rhysd Actionlint Action](https://github.com/cssnr/actionlint-action?tab=readme-ov-file#readme)
- [Zensical Action](https://github.com/cssnr/zensical-action?tab=readme-ov-file#readme)
- [VirusTotal Action](https://github.com/cssnr/virustotal-action?tab=readme-ov-file#readme)
- [Homebrew Action](https://github.com/cssnr/homebrew-action?tab=readme-ov-file#readme)
- [Mirror Repository Action](https://github.com/cssnr/mirror-repository-action?tab=readme-ov-file#readme)
- [Update Version Tags Action](https://github.com/cssnr/update-version-tags-action?tab=readme-ov-file#readme)
- [Docker Tags Action](https://github.com/cssnr/docker-tags-action?tab=readme-ov-file#readme)
- [TOML Action](https://github.com/cssnr/toml-action?tab=readme-ov-file#readme)
- [Update JSON Value Action](https://github.com/cssnr/update-json-value-action?tab=readme-ov-file#readme)
- [JSON Key Value Check Action](https://github.com/cssnr/json-key-value-check-action?tab=readme-ov-file#readme)
- [Parse Issue Form Action](https://github.com/cssnr/parse-issue-form-action?tab=readme-ov-file#readme)
- [Cloudflare Purge Cache Action](https://github.com/cssnr/cloudflare-purge-cache-action?tab=readme-ov-file#readme)
- [Mozilla Addon Update Action](https://github.com/cssnr/mozilla-addon-update-action?tab=readme-ov-file#readme)
- [Package Changelog Action](https://github.com/cssnr/package-changelog-action?tab=readme-ov-file#readme)
- [NPM Outdated Check Action](https://github.com/cssnr/npm-outdated-action?tab=readme-ov-file#readme)
- [Label Creator Action](https://github.com/cssnr/label-creator-action?tab=readme-ov-file#readme)
- [Algolia Crawler Action](https://github.com/cssnr/algolia-crawler-action?tab=readme-ov-file#readme)
- [Create Pull Action](https://github.com/cssnr/create-pull-action?tab=readme-ov-file#readme)
- [Upload Release Action](https://github.com/cssnr/upload-release-action?tab=readme-ov-file#readme)
- [Check Build Action](https://github.com/cssnr/check-build-action?tab=readme-ov-file#readme)
- [Web Request Action](https://github.com/cssnr/web-request-action?tab=readme-ov-file#readme)
- [Get Commit Action](https://github.com/cssnr/get-commit-action?tab=readme-ov-file#readme)

<details><summary>❔ Unpublished Actions</summary>

These actions are not published on the Marketplace, but may be useful.

- [cssnr/create-files-action](https://github.com/cssnr/create-files-action?tab=readme-ov-file#readme) - Create various files from templates.
- [cssnr/draft-release-action](https://github.com/cssnr/draft-release-action?tab=readme-ov-file#readme) - Keep a draft release ready to publish.
- [cssnr/env-json-action](https://github.com/cssnr/env-json-action?tab=readme-ov-file#readme) - Convert env file to json or vice versa.
- [cssnr/push-artifacts-action](https://github.com/cssnr/push-artifacts-action?tab=readme-ov-file#readme) - Sync files to a remote host with rsync.
- [smashedr/update-release-notes-action](https://github.com/smashedr/update-release-notes-action?tab=readme-ov-file#readme) - Update release notes.
- [smashedr/combine-release-notes-action](https://github.com/smashedr/combine-release-notes-action?tab=readme-ov-file#readme) - Combine release notes.

---

</details>

<details><summary>📝 Template Actions</summary>

These are basic action templates that I use for creating new actions.

- [javascript-action](https://github.com/smashedr/javascript-action?tab=readme-ov-file#readme) - JavaScript
- [typescript-action](https://github.com/smashedr/typescript-action?tab=readme-ov-file#readme) - TypeScript
- [py-test-action](https://github.com/smashedr/py-test-action?tab=readme-ov-file#readme) - Dockerfile Python
- [test-action-uv](https://github.com/smashedr/test-action-uv?tab=readme-ov-file#readme) - Dockerfile Python UV
- [docker-test-action](https://github.com/smashedr/docker-test-action?tab=readme-ov-file#readme) - Docker Image Python

Note: The `docker-test-action` builds, runs and pushes images to [GitHub Container Registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry).

---

</details>

For a full list of current projects visit: [https://cssnr.github.io/](https://cssnr.github.io/)

<a href="https://github.com/cssnr/actionlint-action">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=cssnr/actionlint-action&type=date&legend=bottom-right&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=cssnr/actionlint-action&type=date&legend=bottom-right" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=cssnr/actionlint-action&type=date&legend=bottom-right" />
 </picture>
</a>
