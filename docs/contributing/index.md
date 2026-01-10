# Contributing

Thank you for your interest in contributing to the Docuisine project! This page and its children describe the ways you can contribute, as well as some of our policies. This should help guide you through your first Issue or PR.

Even if you cannot contribute code, you can still help Docuisine! The two main things you can help with are testing and creating issues. Contributing to code, documentation, and other non-code components are all outlined in the sections below.

## Issues

We use GitHub extensively to track open issues, new enhancements or features, and other aspects of development.

Please see the [getting help page](../getting-help.md) for help with troubleshooting and finding bugs, and the [documentation on issues](./issues.md) for more information on how to submit good issues or solve them.

## Developing Code

The entire project consists of a Python [FastAPI](https://fastapi.tiangolo.com/) backend server and a JavaScript [ReactJS](https://react.dev/) frontend web client. If you have experience with these languages, we're always grateful for any contributions you might want to make!

For general guidelines on how the project works, including how to set up your development copy, make changes, and guidelines on Pull Requests (PRs), please see the [documentation on contributing code](./development/index.md). Docuisine follows a "fork and PR" methodology; if you're not familiar with this, please see the relevant section.

## Branding & Design

We are open to any changes regarding the branding, theme and User Interface design. For branding and theming, see the [relevent documentation](./artifacts/branding.md) and submit PRs to this [repository](https://github.com/docuisine/assets). For UI design, please submit PRs to this [repository](https://github.com/docuisine/docuisine-react/).

## Adding To Documentation

Documentation is incredibly helpful! All these docs are written using [Zensical](https://zensical.org/). You can find the raw markdown in the [documentation repository](https://github.com/docuisine/documentation). Pull requests are welcome, though please review our [documentation process](./writing-documentation.md) first!

## Testing

Testing is the easiest way to contribute. Simply use Docuisine, and if you run into problems, [let us know](../getting-help.md). This is the most common way we uncover bugs, through a user doing something we hadn't thought about. If the issue does end up being related to the code, a [bug issue](./reporting-issues.md) can then be opened.

## Repos

This section enumerates the repositories of Docuisine and are related with all the previously sections. Should you wish to contribute specifically to their repos, make sure to read their relevent documentation with respect to their domain.

| Repository                                                      | Description                                                 | Domain                              |
| --------------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------- |
| [docuisine](https://github.com/docuisine/docuisine)             | The Python backend of Docuisine                             | [Code](./development/backend.md)    |
| [docuisine-react](https://github.com/docuisine/docuisine-react) | The TypeScript/React backend of Docuisine                   | [Code](./development/frontend.md)   |
| [documentation](https://github.com/docuisine/documentation)     | The docs (this website) for Docuisine written with Zensical | [Docs](writing-documentation.md)    |
| [backlog](https://github.com/docuisine/backlog)                 | For reporting issues that are not repo specific             | [Non-code](issues.md)               |
| [assets](https://github.com/docuisine/assets)                   | Image hosting and branding assets                           | [Non-code](./artifacts/branding.md) |
