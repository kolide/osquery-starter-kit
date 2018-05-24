# Osquery Starter Kit

When you're getting started with osquery, it can be difficult to figure out how to gather up as much high-quality, open-source intelligence as possible and deploy it to your fleet along with your own, custom query packs.

To help with this objective, [Kolide Fleet](https://github.com/kolide/fleet) supports a command-line workflow for managing osquery configuration via source-controlled, code-audited files. The `fleetctl` command-line can be used to "apply" a set of declarative configurations idempotently.

This allows you to setup a CI workflow where CI is the only entity that can update osquery configuration, allowing you to enforce an appropriate level of code review to your osquery SQL deployment proceess. Alternatively, you may just want to `fleetctl apply` your configuration yourself, but you want to have a source-controlled backup of all of your configurations.

This repository aims to be a starting point for people that are looking to deploy osquery and want a code-based workflow that allows for:

- a text-based osquery configuration experience
  - bring your favorite text editor!
- a command-line experiencing for managing osquery deployment configurations
- maximum query re-use
  - use the same query in multiple packs and labels
- code review throughout the configuration management process
- easy sharing of osquery intelligence with others

## Requirements

To use this repo (or a repo like this), you must be using [Kolide Fleet](https://github.com/kolide/fleet) (version 2.0.0 or greater) to manage your osquery deployment and have a locally configured `fleetctl` binary. If your company already uses Kolide Fleet and you'd like to install the `fleetctl` CLI, there are a few supported options. On macOS, you can use the Homebrew package manager:

```
$ brew tap kolide/taps
$ brew install fleet
```

If you'd rather not use Homebrew or you would like to download `fleetctl` on another platform, you can download the latest binaries directly from the [GitHub Releases](https://github.com/kolide/fleet/releases) page.

Once you have the `fleetctl` binary in your path, you must configure your local CLI context to target your remote Fleet instance:

```
$ fleetctl config set --address https://fleet.osquery.tools
[+] Set the address config key to "https://fleet.osquery.tools" in the "default" context
```

Finally, login via the CLI:

```
$ fleetctl login
Log in using the standard Fleet credentials.
Email: mike@arpaia.co
Password:
[+] Fleet login successful and context configured!
```
