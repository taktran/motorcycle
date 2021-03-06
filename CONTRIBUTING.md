# Contributing to MotorcycleJS

We'd highly appreciate your contribution to our source code
and making MotorcycleJS even better. Here are the guidelines,
we'd like you to follow:

 - [Question or Problem?](#question)
 - [Issues and Bugs](#issue)
 - [Feature Requests](#feature)
 - [Submission Guidelines](#submit)
 - [Coding Rules](#rules)
 - [Commit Message Guidelines](#commit)

## <a name="question"></a> Got a Question or Problem?

If you have questions about how to use MotocyleJS, please direct
these to the [Gitter chat room][gitter] or [StackOverflow][stackoverflow].

## <a name="issue"></a> Found an Issue?

If you find a bug in the source code or a mistake
in the documentation, you can help us by submitting an issue
to our [GitHub Repository][github]. Even better, you can submit
a Pull Request with a fix.

**Please see the Submission Guidelines below**.

## <a name="feature"></a> Want a Feature?

You can request a new feature by submitting an issue to our
[GitHub Repository][github]. If you would like to implement
a new feature, then consider what kind of change it is:

* **Major Changes** that you wish to contribute to the project
should be discussed first on our [Gitter Dev chat room][gitter-dev]
so that we can better coordinate our efforts, prevent duplication
of work, and help you to craft the change so that
it is successfully accepted into the project.
* **Small Changes** can be crafted and submitted to the
[GitHub Repository][github] as a Pull Request.

## <a name="docs"></a> Want a Doc Fix?

If you want to help improve the docs, it’s a good idea
to let others know what you’re working on to minimize duplication
of effort. Before starting, check out the issue queue
for [Docs Only](https://github.com/motorcyclejs/motorcycle/issues?q=is%3Aopen+is%3Aissue+label%3A%22type%3A+docs%22).
Comment on an issue to let others know what you’re working on,
or create a new issue if your work doesn’t fit within the scope
of any of the existing doc fix projects.

You should also make sure that your commit message is labeled
"docs():" and follows the **Git Commit Guidelines**
outlined below.

## <a name="submit"></a> Submission Guidelines

### Submitting an Issue
Before you submit your issue search the archive, maybe your
question was already answered.

If your issue appears to be a bug, and hasn’t been reported, open
a new issue. Help us to maximize the effort we can spend fixing 
issues and adding new features, by not reporting duplicate issues. 
Providing the following information will increase the chances 
of your issue being dealt with quickly:

* **Overview of the Issue** - if an error is being thrown, 
  a non-minimized stack trace helps.
* **Motivation for or Use Case** - explain why this is a bug 
  for you.
* **Motorcycle Version(s)** - is it a regression?
* **Browsers and Operating System** - is this a problem with 
  all browsers or only IE8?
* **Reproduce the Error** - provide a live example 
  (using [Plunker][plunker], [JSFiddle][jsfiddle], 
  or [JSBin][jsbin]) or an unambiguous set of steps.
* **Related Issues** - has a similar issue been reported before?
* **Suggest a Fix** - if you can’t fix the bug yourself, perhaps 
  you can point to what might be causing the problem 
  (line of code or commit).

Here is a great example of a well defined issue: 
https://github.com/angular/angular.js/issues/5069

**If you get help, help others. Good karma rules!**

### Submitting a Pull Request
Before you submit your pull request, consider 
the following guidelines:

* Search [GitHub](https://github.com/motorcyclejs/motorcycle-core/pulls)
  for an open or closed Pull Request that relates to your 
  submission. You don’t want to duplicate effort.
* Make your changes in a new git branch:

     ```shell
     git checkout -b fix/issue-#n develop
     ```

* Create your patch, **including appropriate test cases**.
* Follow our [Coding Rules](#rules).
* Run the full Motorcycle test suite, and ensure that 
  all tests pass.
* Commit your changes using a descriptive commit message that 
  follows our [commit message conventions](#commit-message-format) 
  and passes our commit message pre-submit hook 
  `validate-commit-message`. Adherence 
  to the [commit message conventions](#commit-message-format)
  is required because release notes are automatically generated
  from these messages.

     ```shell
     git commit -a
     ```
  Note: the optional commit `-a` command line option will 
  automatically "add" and "rm" edited files.

* Build your changes locally to ensure all the tests pass:

    ```shell
    npm test
    ```

* Push your branch to GitHub:

    ```shell
    git push origin fix/issue-#n
    ```

* In GitHub, send a pull request to `motorcycle-repo:develop`.
* If we suggest changes then:
  * Make the required updates.
  * Re-run the Motorcycle test suite to ensure tests 
    are still passing.
  * Rebase your branch and force push to your GitHub repository 
    (this will update your Pull Request):

    ```shell
    git rebase -i fix/issue-#n
    git push origin fix/issue-#n -f
    ```

That’s it! Thank you much for your contribution!

#### After your pull request is merged
After your pull request is merged, you can safely delete your 
branch and pull the changes from the main (upstream) repository:

* Delete the remote branch on GitHub either through the GitHub 
  Web UI or your local shell as follows:

    ```shell
    git push origin --delete fix/issue-#n
    ```

* Check out the develop branch:

    ```shell
    git checkout develop -f
    ```

* Delete the local branch:

    ```shell
    git branch -D fix/issue-#n
    ```

* Update your develop branch with the latest upstream version:

    ```shell
    git pull --ff upstream develop
    ```

## <a name="rules"></a> Coding Rules
To ensure consistency throughout the source code, keep these 
rules in mind as you are working:

* All features or bug fixes **must be tested** by one 
  or more tests.
* All public API methods **must be documented**. To see how 
  we document our APIs, please check out 
  the existing [docs][docs].
* We follow the rules contained in [Style Guide][js-style-guide]:
    * Wrap all code at **80 characters**.
    * Instead of complex inheritance hierarchies, 
      we **prefer simple objects**. We use prototypal inheritance 
      only when absolutely necessary.
    * We **love functions and closures** and, whenever possible, 
      prefer them over objects.
    * To write concise code that can be better minimized, 
      we **use aliases internally** that map to the external API. 
      See our existing code to see what we mean.
    * We **don’t go crazy with type annotations** for private 
      internal APIs unless it’s an internal API that is used 
      throughout MotorcycleJS. The best guidance is to do what 
      makes the most sense.

## <a name="commit"></a> Git Commit Guidelines

We have very precise rules over how our git commit messages 
can be formatted. This leads to **more readable messages** that 
are easy to follow when looking through the **project history**. 
But also, we use the git commit messages to **generate 
the MotorcycleJS change logs**.

The commit message formatting can be added using a typical 
git workflow or through the use of a CLI wizard 
([Commitizen](https://github.com/commitizen/cz-cli)). 
To use the wizard, run `npm run commit` in your terminal after 
staging your changes in git.

### Commit Message Format
Each commit message consists of a **header**, a **body**, and 
a **footer**. The header has a special format that includes 
a **type**, a **scope**, and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header 
is optional.

Any line of the commit message cannot be longer 80 characters. 
This allows the message to be easier to read on GitHub, as well 
as in various git tools.

### Revert
If the commit reverts a previous commit, it should begin with 
`revert(): `, followed by the header of the reverted commit. 
In the body, it should say: `This reverts commit <hash>.`, where 
the hash is the SHA of the commit being reverted.

### Type
Must be one of the following:

* **feat**: A new feature.
* **fix**: A bug fix.
* **docs**: Documentation only changes.
* **style**: Changes that do not affect the meaning of the code 
  (white-space, formatting, missing semi-colons, etc.)
* **refactor**: A code change that neither fixes a bug nor adds 
  a feature.
* **perf**: A code change that improves performance.
* **test**: Adding missing tests.
* **chore**: Changes to the build process or auxiliary tools 
  and libraries such as documentation generation.

### Scope
The scope could be anything specifying place of the commit change. 
For example, `core`, `README`, `DOM`, etc.

### Subject
The subject contains succinct description of the change:

* use the imperative, present tense: "change" not "changed" 
  nor "changes",
* don't capitalize first letter, and
* no dot (.) at the end.

### Body
Just as in the **subject**, use the imperative, present tense: 
"change" not "changed" nor "changes". The body should include 
the motivation for the change and contrast this with 
previous behavior.

### Footer
The footer should contain any information about **Breaking 
Changes** and is also the place to reference GitHub issues that 
this commit **Closes**.

**Breaking Changes** should start with the words `BREAKING 
CHANGE:` with a space or two newlines. The rest of the commit 
message is then used for this.

A detailed explanation can be found in this 
[document][commit-message-format].



[gitter-dev]: https://gitter.im/motorcyclejs
[commit-message-format]: https://docs.google.com/document/d/1QrDFcIiPjSLDn3EL15IJygNPiHORgU1_OOAqWjiDU5Y/edit#
[github]: https://github.com/motorcyclejs/motorcycle
[gitter]: https://gitter.im/motorcyclejs/motorcycle-core
[jsbin]: http://jsbin.com/
[jsfiddle]: http://jsfiddle.net/
[plunker]: http://plnkr.co/edit
[stackoverflow]: http://stackoverflow.com/questions/tagged/motorcyclejs
