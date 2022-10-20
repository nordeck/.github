# Contribution Guidelines

We are looking forward to your contributions. Please take a moment to read these Contribution Guidelines.

If not otherwise noted, our projects are released under the Apache 2.0 License, and original creations contributed to this repo are accepted under the same license.

If you have any questions, [reach out to us](./SUPPORT.md).

## Coding Guidelines

All our code is formatted using [`prettier`](https://prettier.io/).
You can run prettier on your own.
We have a pre-commit hook and a pipeline step in the CI to verify that all code is formatted properly.

We are using [`eslint`](https://eslint.org/) to avoid common problems.
The rule set is similar in most projects, but there might be special cases.

We use ADRs ([Architectual Decision Records](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)) to keep track of bigger decissions we did.
They are placed at `/docs/adr` in each repository and might give additional guidelines.

Testing is important for us to ensure a good quality.
If you find bugs, or implement new features, make sure that they are covered by automated tests.
These can either be unit/integration tests or end-to-end tests.

If you make changes to the event formats, configuration and the like, make sure to update the related documentation.

These are general guidelines for all projects, but there might be individual ones in each project.

## Submitting PRs

Pull Request are used to contribute to our projects.
When creating a PR, please take a moment to fill out the template at the top.
It contains a short checklist to create a great PR, which makes it easier for us to review your PR.

If you plan bigger changes, please reach out to us first via chat or by creating an issue.

## DCO

For each contribution, you have to sign a [Developers Certificate of Origin (DCO)](https://developercertificate.org/).
A DCO is a lightweight way for a developer to certify that they wrote or otherwise have the right to submit code or documentation to a project.

```plain
By making a contribution to this project, I certify that:

(a) The contribution was created in whole or in part by me and I
    have the right to submit it under the open source license
    indicated in the file; or

(b) The contribution is based upon previous work that, to the best
    of my knowledge, is covered under an appropriate open source
    license and I have the right under that license to submit that
    work with modifications, whether created in whole or in part
    by me, under the same open source license (unless I am
    permitted to submit under a different license), as indicated
    in the file; or

(c) The contribution was provided directly to me by some other
    person who certified (a), (b) or (c) and I have not modified
    it.

(d) I understand and agree that this project and the contribution
    are public and that a record of the contribution (including all
    personal information I submit with it, including my sign-off) is
    maintained indefinitely and may be redistributed consistent with
    this project or the open source license(s) involved.
```

You sign-off that you adhere to these requirements by adding a `Signed-off-by` line to commit messages.

```plain
This is my commit message

Signed-off-by: Random J Developer <random@developer.example.org>
```

Git has a `-s` command line option to append this automatically to your commit message:

```sh
$ git commit -s -m 'This is my commit message'
```

## Changelog and Versioning

We use [changesets](https://github.com/atlassian/changesets) to help us prepare releases.
They help us make sure that every project affected by a change gets a proper version number and an entry in its `CHANGELOG.md`.
To make the process of generating releases easy, it helps when you include changesets with your pull requests.

### When to use a changeset?

Any time a patch, minor, or major change aligning to [Semantic Versioning](https://semver.org) is made, a changeset should be used.
Changesets are not needed for changes that do not affect the published version of each project, for example changes to tests, in-line source code comments, or documentation.

### How to create a changeset

1. Run `yarn changeset`
2. Select which packages you want to include a changeset for (optional if there is only a single one)
3. Select impact of change that you're introducing, using `major` for breaking changes, `minor` for new features, and `patch` otherwise. We use `minor` instead of `major` changes while packages are below version `1.0.0`.
4. Explain your changes in the generated changeset, you can include screenshots too!.
5. Add generated changeset to Git
6. Push the commit with your changeset to the branch associated with your PR

For more information, checkout [adding a changeset](https://github.com/atlassian/changesets/blob/master/docs/adding-a-changeset.md) documentation in the changesets repository.
