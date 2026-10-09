# Security

Agentbox starts coding agents on your machine, so a security problem in it can
matter a great deal. Thank you for reporting one privately.

## How to report

Use [private vulnerability reporting for this fork](https://github.com/mlnomadpy/agentbox/security/advisories/new),
or the **Security** tab of the repository affected, then **Report a vulnerability**. Please do not open a public issue or pull request
for it.

Include what an attacker could do, the steps to reproduce it, and the version
or commit you tested.

## What happens next

Maintainers assess reports as availability permits. Coordinate disclosure with
the maintainer before publishing details; fixes and disclosure timing depend on
impact and verification. Request attribution or anonymity in your report.

## What counts

Anything that lets something other than the person using Agentbox act on their
machine or read their data, including:

- an agent getting past an approval it should have needed;
- a worker receiving an API key, or the user's own browser (`--chrome`);
- anything leaving the machine that the privacy policy says does not;
- code in a pull request, a dependency or a workflow that would run with more
  access than it should.
