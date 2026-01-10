# Issues

This page discusses how to open issues, including the policies and procedures of the Docuisine project around handling issues.

Issues should only detail software bug reports or suggestions.

All other discussions, including initial troubleshooting, should be directed towards our [help channels](../getting-help.md).

## Reporting issues

Once you're ready to open an issue, please see [this page](https://github.com/docuisine/backlog/issues)!

### Reporting Bugs

When writing a bug issue, please ensure you capture as much relevant detail as possible - this is very important to assist in troubleshooting and triaging/investigating the issue. Some useful elements include:

- How you installed Docuisine (upgrade or fresh install)
- What platform and operating system you are using (Debian, Arch, Docker, etc.)
- What you were doing that caused the issue to appear
- Any relevant log output
- Any non-standard configurations you use

Bugs should be tagged with `[BUG]:` at the beginning of their title. This will later be removed by the Docuisine team when assigning labels. To assist in triaging, if you know which other [label(s)](https://github.com/docuisine/backlog/labels) should be applied to your issue, please add them after the `bug` label.

Bugs should be reproduceable. That is, you should be able to have determined through troubleshooting how to replicate the issue. While one-time bugs should not be ignored, if they're difficult or impossible to reproduce, it's likely very hard to fix them. Please attempt to reproduce the bug before filing the issue and include the smallest test case you can to demonstrate it.

If you ever need assistance for troubleshooting or opening an issue, please [contact the community](../getting-help.md) and we'll try to help you out!

## Solving issues

Backlog issues are issues that have already been report/written up and remain to be completed. Resolving these existing issues is one of the main ways of contributing to Docuisine.

![Backlog Dashboard](https://raw.githubusercontent.com/docuisine/docuisine/refs/heads/master/docs/docs/assets/contributing/development/backlog-dashboard.png)

To stay on top of existing issues, head over to the [backlog dashboard](https://github.com/orgs/docuisine/projects/1) to see issues that have been `Accepted` and are ready to be completed. These issues are concerned with both code and non-code issues so make sure to read the relevant documentation for [contributing code changes](/documentation/contributing/development/) and [writing documentation](/documentation/contributing/writing-documentation/).
