# Auto-Remediation with Puppet and Configuration Management

## Background Context

During my tenure at SlideShare, I developed an auto-remediation tool named Skynet, which utilized Puppet for managing and scaling our cloud infrastructure. Skynet leveraged MCollective for parallel job execution, enabling actions across multiple servers simultaneously. However, a critical bug in the code resulted in passing `nil` to the filter method, which unintentionally targeted all servers for termination.

### Consequences:
- MCollective interpreted `nil` as a directive to terminate all servers.
- 75% of our document conversion infrastructure was shut down.
- Users were unable to convert PDFs, PowerPoints, and videos.

Thanks to Puppet's configuration management capabilities, we swiftly restored our infrastructure within an hour. Automating this recovery process with Puppet prevented prolonged downtime and manual errors that would have complicated recovery efforts.

[![Me at work](https://x.com/devopsreact/status/836971570136375296)](https://x.com/devopsreact/status/836971570136375296)

## Resources

### Read or watch:
- [Intro to Configuration Management](link)
- [Puppet resource type: file](link) (check “Resource types” for all manifest types in the left menu)
- [Puppet’s Declarative Language: Modeling Instead of Scripting](link)
- [Puppet lint](link)
- [Puppet emacs mode](link)

## Requirements

### General
- All files interpreted on Ubuntu 20.04 LTS
- All files end with a new line
- **Mandatory** README.md file at the project's root folder

### Puppet Manifests
- Must pass puppet-lint version 2.1.1 without errors
- Must run without errors
- First line of each Puppet manifest must be a comment explaining its purpose
- Puppet manifest files must have the extension `.pp`

### Note on Versioning
- Ubuntu 20.04 VM should have Puppet 5.5 preinstalled.

## Installation Guide

### Install Puppet

```bash
$ apt-get install -y ruby=1:2.7+1 --allow-downgrades
$ apt-get install -y ruby-augeas
$ apt-get install -y ruby-shadow
$ apt-get install -y puppet

