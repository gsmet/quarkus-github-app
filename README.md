# Quarkus GitHub App

[![Version](https://img.shields.io/maven-central/v/io.quarkiverse.githubapp/quarkus-github-app?logo=apache-maven&style=for-the-badge)](https://central.sonatype.com/artifact/io.quarkiverse.githubapp/quarkus-github-app)
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-9-orange.svg?style=for-the-badge)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

<p align="center"><img src="https://design.jboss.org/quarkus/bot/final/images/quarkusbot_full.svg" width="128" height="128" /></p>

**Develop your GitHub Apps in Java with Quarkus**

> [!TIP]
> Interested in GitHub Actions? Have a look at the [Quarkus GitHub Action extension](https://github.com/quarkiverse/quarkus-github-action/).

Quarkus GitHub App is a [Quarkus](https://quarkus.io) extension
that allows to create GitHub Apps in Java with very little boilerplate.

Think of it as [Probot](https://probot.github.io) for Java with some cool additional features.

And yes, it supports generating native executables with GraalVM or Mandrel.

Your application will look like:

```java
class MyGitHubApp {

	void onOpen(@Issue.Opened GHEventPayload.Issue issuePayload) throws IOException {
		issuePayload.getIssue().comment("Hello from MyGitHubApp");
	}
}
```

And that's it.

The code above listens to the `issues.opened` GitHub event and posts a comment in each opened issue.

That's for the basics but it supports the GitHub REST API, execution of GraphQL queries, YAML or JSON config files in your repository...

It relies on a [Smee.io proxy](https://smee.io) during the development of the app to redirect GitHub events towards your local instance with no hassle.

With the [`command-airline` additional extension](https://quarkiverse.github.io/quarkiverse-docs/quarkus-github-app/dev/commands.html), you can also easily develop comment-based commands (e.g. `@bot do something`).

Finally, it comes with a nice and searchable Replay UI:

> ![Replay UI](/docs/modules/ROOT/assets/images/replay-ui.png?raw=true "Replay UI")

## Compatibility

Quarkus GitHub App 2.x is compatible with Quarkus 3.x.

We recommend using the latest versions of both for the best experience.

## Documentation

To get you started (and more!), please refer to [the extensive documentation](https://quarkiverse.github.io/quarkiverse-docs/quarkus-github-app/dev/index.html).

Anything unclear or missing in the documentation? Please [open an issue](https://github.com/quarkiverse/quarkus-github-app/issues/new), we will address it quickly.

## Examples

* [Quarkus GitHub Bot](https://github.com/quarkusio/quarkus-github-bot)
* [Hibernate GitHub Bot](https://github.com/hibernate/hibernate-github-bot)
* [Debezium GitHub Bot](https://github.com/debezium/debezium-github-bot)
* [Keycloak GitHub Bot](https://github.com/keycloak/keycloak-github-bot)
* [Milestone Check GitHub App](https://github.com/scholzj/milestone-check)

## How?

The Quarkus GitHub App extension uses the [Hub4j GitHub API](https://github.com/hub4j/github-api)
to parse the webhook payloads and handle the [GitHub REST API](https://docs.github.com/en/rest) calls.

It can also execute GraphQL queries towards the [GitHub GraphQL API](https://docs.github.com/en/graphql) via the SmallRye GraphQL Client.

The rest of the extension is Quarkus magic - mostly code generation with [Gizmo](https://github.com/quarkusio/gizmo/) -
to get everything wired.

It also leverages [Reactive Routes](https://quarkus.io/guides/reactive-routes),
[CDI events (both sync and async)](https://quarkus.io/guides/cdi#events-and-observers),
and [Caffeine](https://quarkus.io/guides/cache).

> ![Architecture](/docs/modules/ROOT/assets/images/architecture.png?raw=true "Architecture")

## Status

This extension is considered stable and is used in production.

## License

This project is licensed under the [Apache License Version 2.0](./LICENSE.txt).

## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tbody>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/gsmet/"><img src="https://avatars1.githubusercontent.com/u/1279749?v=4?s=100" width="100px;" alt="Guillaume Smet"/><br /><sub><b>Guillaume Smet</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/commits?author=gsmet" title="Code">💻</a> <a href="#maintenance-gsmet" title="Maintenance">🚧</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/yrodiere"><img src="https://avatars1.githubusercontent.com/u/412878?v=4?s=100" width="100px;" alt="Yoann Rodière"/><br /><sub><b>Yoann Rodière</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/commits?author=yrodiere" title="Code">💻</a> <a href="#maintenance-yrodiere" title="Maintenance">🚧</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/jtama"><img src="https://avatars.githubusercontent.com/u/39991688?v=4?s=100" width="100px;" alt="jtama"/><br /><sub><b>jtama</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/commits?author=jtama" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/joelmarty"><img src="https://avatars.githubusercontent.com/u/134835?v=4?s=100" width="100px;" alt="Joël Marty"/><br /><sub><b>Joël Marty</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/commits?author=joelmarty" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://hollycummins.com"><img src="https://avatars.githubusercontent.com/u/11509290?v=4?s=100" width="100px;" alt="Holly Cummins"/><br /><sub><b>Holly Cummins</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/commits?author=holly-cummins" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://stackoverflow.com/users/1392277/lppedd"><img src="https://avatars.githubusercontent.com/u/19871649?v=4?s=100" width="100px;" alt="Edoardo Luppi"/><br /><sub><b>Edoardo Luppi</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/issues?q=author%3Alppedd" title="Bug reports">🐛</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://www.ebullient.dev"><img src="https://avatars.githubusercontent.com/u/808713?v=4?s=100" width="100px;" alt="Erin Schnabel"/><br /><sub><b>Erin Schnabel</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/commits?author=ebullient" title="Code">💻</a></td>
    </tr>
    <tr>
      <td align="center" valign="top" width="14.28%"><a href="https://www.ryandens.com"><img src="https://avatars.githubusercontent.com/u/8192732?v=4?s=100" width="100px;" alt="Ryan Dens"/><br /><sub><b>Ryan Dens</b></sub></a><br /><a href="https://github.com/quarkiverse/quarkus-github-app/commits?author=ryandens" title="Code">💻</a></td>
      <td align="center" valign="top" width="14.28%"><a href="https://github.com/Munken"><img src="https://avatars.githubusercontent.com/u/773660?v=4?s=100" width="100px;" alt="Michael Munch"/><br /><sub><b>Michael Munch</b></sub></a><br /><a href="#ideas-Munken" title="Ideas, Planning, & Feedback">🤔</a> <a href="https://github.com/quarkiverse/quarkus-github-app/pulls?q=is%3Apr+reviewed-by%3AMunken" title="Reviewed Pull Requests">👀</a></td>
    </tr>
  </tbody>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!

## Acknowledgements

Quarkus GitHub App uses the following Open Source projects:

* [Quarkus](https://quarkus.io)
* [Hub4j GitHub API](https://github.com/hub4j/github-api)
* [Airline](https://rvesse.github.io/airline/)
* [Event Stream Client for Server-Sent Events](https://github.com/LupCode/java-sse-client)
* And for the Replay UI: [Fomantic UI](https://fomantic-ui.com), [Vue.js](https://vuejs.org) and [jQuery](https://jquery.com)
