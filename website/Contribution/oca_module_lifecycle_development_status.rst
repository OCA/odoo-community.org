##################################
|TITLE| (|DATE|)
##################################

.. |TITLE| replace:: OCA Maturity Levels and Development Status Policy
.. |DATE| replace:: 2018/08/24

.. contents:: Table of contents
    :depth: 4

.. sectnum::

Introduction
============
The requirements to merge code into OCA projects depend on the module's
maturity level.

The OCA uses the following maturity levels for the modules stored in the
Github repository and published in PyPi platform:

-  **Alpha:** Unstable, for development or testing purpose

-  **Beta:** Pre-production quality but with potential instability

-  **Production/Stable:** suitable for production environment

-  **Mature:** In Production level since more than one version and
   actively maintained.

This is consistent with the terminology used on PyPi, and the allowed
values are the same as the ones used by PyPi.

A module maturity level is stored in the **development\_status** key of
the standard manifest of the module (\_\_manifest\_\_.py).

For better visibility of the development level, it is highlighted in the
module README file. Thanks to automated documentation script (using a
DESCRIPTION.rst and other companion documentation files), the maturity
level badge is automatically added by a nightly script, that compiles
all the separate RST fragments into a single README.rst file.

Modules in all development status are hosted in the same repositories
and branches. You will find Beta modules alongside Stable ones: for this
reason, you have to make sure to check the README or manifest before
deciding to use a module in production environment.

A module’s development\_status can be different for different versions.
A “mature” or “stable” module in a version can start as “stable” or
“beta” in the next branch, as a step towards maturity.

All modules, regardless of their development status, will be published
on PyPi and on the Odoo AppStore.

Next we describe in detail what each 'development status' means, what
can be expected by users, and what are the requirements for modules to
be assigned each maturity level.

When no development\_status is set in the manifest, Beta is assumed.

**Alpha and Beta modules**
==========================

Alpha and Beta modules allow for the incubation of OCA Stable modules.
They enable the work to be split into several smaller pull requests,
that are easier to review and make it easier to divide the work between
several people.

Should have at least one peer review.

No minimum coverage percentage required.

Each pull request is an iteration providing a correct set of features.
The corresponding code should always pass CI checks;
since there is no minimum coverage percentage required,
the coverage CI check can be failing.
Right now, the coverage CI check is managed with Codecov.

Since these modules are a work in progress toward a “stable” module,
they are not suitable for use in production. The design and
implementation may change without notice in incompatible ways, the
development work may halt, and it is even possible that it may be
abandoned and deleted from the repository.

The suggested module incubation workflow looks like this:

#. Create a “WIP” Issue for the module, used to coordinate the work and
   different PRs related to it. It should state the final goal and
   describe the next work units to be done.

#. Create the PRs implementing the work units described in the WIP
   Issue. They must pass CI tests and peer review.

#. Once contributors feel that the module is complete, promotion to
   “stable” status can be proposed through a PR changing the
   **development\_status** manifest key.

This workflow can also be extended to support a functional design stage,
prior to the implementation:

-  Before the “WIP” Issue, an “RFC” issue (complemented by a Google Doc
   or similar, if necessary) can be created for an initial
   discussion of the scope, desired features and the implementation
   design outline.

-  Once a “WIP” Issue is created, a first PR can create the skeleton of
   the new module, including the basic DESCRIPTION.rst, and a
   SPECS.rst file for the specifications and technical design.

The Alpha stage is not required, but it may be useful to signal that the
module is not expected to work as planned yet (or at all). It is in the
early stages of design and construction, and trying it on Runboat is
pointless

Changing the development status to Beta is a way to signal reviewers and
functional testers that the module should be usable enough to be tested.

As a summary, alpha and beta modules:

-  Must at all times follow the OCA coding standards and ensure CI
   green builds (coverage is optional).

-  Must be correctly installed by the OCA Runboat, without conflicting
   with other installed modules, allowing people to try them

-  Are recommended to have a “WIP” Issue to list the pending tasks and
   coordinate the work around them.

-  Are recommended to have at least one peer review before merging PRs.

**Stable modules**
==================

Stable modules are adequate for production use, and meet all the
original OCA quality requirements: green CI build passing all current
mandatory checks, and peer reviewed by at least two other people.

They have an “API stable” policy similar to the Odoo policy for stable
branches, ensuring that extensions won't break, but more permissive,
allowing for feature additions and improvements.

As a summary, “stable” modules:

-  Must at all times follow the OCA coding standards and ensure CI
   green builds (coverage is optional).

-  Must be correctly installed by the OCA Runboat, without conflicting
   with other installed modules, allowing people to try them.

-  Must have some tests.

-  Must depend only on Stable and Mature modules..

-  Two peer reviews and a review period of at least five days are needed
   for merge. The review period can be shorter if three or more
   reviewers approve the PR.

-  Must have code formatted

**Mature modules**
==================

Mature modules not only meet the stable criteria, but are also known to
be actively maintained. Usually these are modules in use in several
deployments, and maintained by more than one party. They typically
survived major version changes, having version ports, and there is a
reasonable expectation for this to happen in future major versions.

Mature modules:

-  Must meet all "Stable" module criteria.

-  Are recommended to also exists for at least one previous Odoo
   version.

-  Must have tests with good code coverage.

-  Must not have lint beta message warnings.

-  Must have user documentation (at least a detailed USAGE.rst).

-  Are recommended to have a changelog (HISTORY.rst).

-  Must be stable across Odoo versions: in case that significant changes
   are made to the data model, automatic migration OpenUpgrade
   scripts are provided. API breakages must be documented clearly,
   and be accompanied with a change in the major version number.

-  Must have at least 2 independent contributors.

-  Must have at least one declared maintainer.

-  Must depend only on Mature modules.

-  Must not have relevant overlap with existing Mature modules (unless a
   good justification is given, evaluated by the relevant PSC).

   .. note::
      The canonical URL to this document is https://odoo-community.org/page/development-status
