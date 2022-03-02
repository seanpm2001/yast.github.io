YaST Contribution Guidelines
============================

YaST is an open source project and as such it welcomes all kinds of
contributions. If you decide to contribute, please follow these guidelines to
ensure the process is effective and pleasant both for you and the YaST maintainers.

There are two main forms of contribution: reporting bugs and performing code
changes.

Bug Reports
-----------

![&#26a0;](images/warning.svg)
*For reporting security issues read the
[Security](https://github.com/yast/.github/blob/master/SECURITY.md)
documentation, the security related bugs need a special handling.*

If you find a problem, please report it either using
[Bugzilla](https://bugzilla.suse.com/enter_bug.cgi?format=guided&product=openSUSE+Tumbleweed&component=YaST2)
or GitHub issues (in the respective repository).

When creating a bug report, please follow our [bug reporting
guidelines](https://en.opensuse.org/openSUSE:Report_a_YaST_bug).

We can't guarantee that every bug will be fixed, but we'll try.

Code Changes
------------

We welcome all kinds of code contributions, from simple bug fixes to significant
refactorings and implementation of new features. However, before making any
non-trivial contribution, get in touch with us first — this can prevent wasted
effort on both sides. Also, have a look at our [development
documentation](http://en.opensuse.org/openSUSE:YaST_development).

![&#26a0;](images/warning.svg)
*For sending security related fixes read the
[Security](https://github.com/yast/.github/blob/master/SECURITY.md)
documentation.*

To send us your code change, use GitHub pull requests. The workflow is as
follows:

  1. Fork the project.

  2. Create a topic branch based on `master`.

  3. Implement your change, including tests (if possible). Make sure you adhere to the Ruby style guide by using [rubocop](https://github.com/rubocop/rubocop): `rake check:rubocop`.

  4. Update the package version (in `packages/*.spec`, usually by
     `rake version:bump`) and add a new entry to the `package/*.changes` file
     (by `osc vc package`).
     For bigger changes or changes which need longer discussion it is advised to
     add this as a separate last commit so it can be easily updated when another
     change is merged in the meantime.

  5. Make sure your change didn't break anything by building the RPM package
     (`rake osc:build`). The build process includes running the full testsuite.

  6. Publish the branch and create a pull request.

  7. YaST developers will review your change and possibly point out issues.
     Adapt the code under their guidance until they are all resolved.

  8. Finally, the pull request will get merged or rejected.

See also [GitHub's guide on
contributing](https://help.github.com/articles/fork-a-repo).

If you want to do multiple unrelated changes, use separate branches and pull
requests.

### Commits

Each commit in the pull request should do only one thing, which is clearly
described by its commit message. Especially avoid mixing formatting changes and
functional changes into one commit. When writing commit messages, adhere to
[widely used
conventions](http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html).

If your commit is related to a bug in Bugzilla or an issue on GitHub, make sure
you mention it in the commit message for cross-reference. Use format like
bnc#775814 or gh#yast/yast-foo#42. See also [GitHub
autolinking](https://help.github.com/articles/github-flavored-markdown#references)
and [openSUSE abbreviation
reference](http://en.opensuse.org/openSUSE:Packaging_Patches_guidelines#Current_set_of_abbreviations).

Additional Information
----------------------

If you have any question, feel free to ask at the [development mailing
list](https://lists.opensuse.org/archives/list/yast-devel@lists.opensuse.org/) or at the
[#yast](https://web.libera.chat/#yast) IRC channel.
We'll do our best to provide a timely and accurate answer.
