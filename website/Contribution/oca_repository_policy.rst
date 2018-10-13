##################################
|TITLE| (|DATE|)
##################################

.. |TITLE| replace:: OCA Repository Policy
.. |DATE| replace:: 2018/08/24

.. contents:: Table of contents
    :depth: 4

.. sectnum::

Contributing new features to the OCA
====================================

**OCA aims to provide a reference business feature library.**

-  Features are provided by Odoo addon modules.

-  Addons modules are organized in code repositories, by topic: App or
   functional area, vertical area, or country (localization). When
   relevant, we may sub-topics with specific repositories.

-  OCA addon modules are expected to be quality checked, stable, and
   relevant.

**The OCA high standards are needed for the quality reference library
goal, but entail a hard process, that can limit contributor motivation
and participation**

This is so because a proposed module will only be merged once it passes
all OCA standards:

-  Functional review:

   -  Validate the right module name and repository to host the feature.

   -  Validate overlap, conflicts and synergies with existing OCA
      features.

   -  Validate functional design.

-  Technical Review:

   -  Naming guidelines.

   -  Coding guidelines and best practices.

   -  Having and passing automated tests.

   -  Pass automated CI checks.

**The incubation approach was introduced to lower the barrier to the
entry of new contributors and ease collaboration.** Code that is
included in the OCA under the incubation process is intended to be
actively improved until it reaches a Stable level, or can stands as a
challenger to an existing Stable module providing a similar feature.
Incubation code that was abandoned should be deleted.

**Incubated modules are hosted in the same repositories as stable ones,
but are labelled with a Alpha or Beta maturity level.**

They allow for an iterative development, where the module is gradually
improved until it can reach the Stable status, adding a new feature to
the library, or even challenging and replacing the current reference
feature implementation.

**Incubation repositories can be added under the OCA**, as a way to
bring a significant body of work into the OCA, and start the long
process of evolving it to meet the OCA standards and integrate perfectly
with the already existing OCA features.

Typically the modules hosted in an incubation repository aim to be moved
to a final repository, as Beta or Stable maturity levels, once some
minimal criteria set by the maintainers is met. The horizon is for the
incubation repository to be extinct, unless it adds a whole new topic to
the OCA that the relevant PSC decides deserving a dedicated repository.

Summary
=======

The OCA aims to provide a **quality**, **stable** and **relevant** set
of addon modules. To achieve this, a few practices have been set in
place:

-  For **quality**, the code goes through automated checks, and must be
   peer reviewed.

-  A **stability** policy, similar to the Odoo “API stable” policy, is
   enforced.

-  For **relevance**, the maintainer curate features to ensure they are
   generic enough and don’t significantly overlap.

For a new module to be accepted into the OCA, all the above criteria
should be met. This can be a challenge for those first contributing to
the OCA. **Module Maturity Levels were introduced to ease contributing
modules originally developed outside the OCA ecosystem**. While modules
in Stable and Mature stages still need to meet all the criteria, in
Alpha and Beta stages they are eased, and only the automated checks are
required to pass.

General principles
==================

The OCA aims to provide a **quality**, **stable** and **relevant** set
of addon modules. To achieve this, a few practices have been set in
place.

To achieve **quality**, the addon modules code goes through automated
checks, and must be peer reviewed. The code is tested along with the
other OCA modules related to the same functional area, to make sure
modules are compatible and work well with each other.

To achieve this, modules in the same functional perimeter are kept in
the same repository. Code repositories need to be kept at a manageable
size, so sometimes they are split into several smaller and more focused
ones. For example OCA/project was split into OCA/project, OCA/contract
and OCA/project-agile.

A **stability** policy is enforced, meaning that, for the same Odoo
version, a module can’t have changes that break current installations or
custom modules depending on it, similar to the Odoo “API stable” policy.
It is more flexible than Odoo’s, since it allows for additions, as long
as the already existing names and extension points are not changed.

The OCA maintainers also curate the proposed features, in order to keep
**relevance**.

They should ensure that proposed feature are generic enough to be useful
to other people. If a module is too specific to a particular
implementation, it probably has little interest for the community in
general. The proposed features also should not significantly overlap
with the other existing features, so that the OCA proposed one reference
solution for each problem/need. This selection of the best
implementation provides great value to the code users. And it gives
incentives to improving the existing features to cover more use cases,
rather than keeping different implementations, each with different use
cases in mind, increasing complexity for code users.

The above has been policy for the code base maintained under the OCA
umbrella, and with the introduction of the Maturity Levels it is
expected to **keep being followed for addon modules in Stable and Mature
levels**.

Considerations on the module creation economics
===============================================

As a preamble it is worth considering why people create addon modules,
and why they are willing to contribute them to the OCA.

A key idea is that for a module to be built, someone has to fund that
work. While some modules may be created just for fun, pursuing some
personal interests, the vast majority is built by people working for
customers, funded by those customers, either your employer or a customer
of your employer.

This means that the code will be first written having these customer
specific requirements in mind. In some cases it will be too specific,
and not useful for other people; in other it may be a generally useful
feature, but most of the time it will be a mix of both: a potentially
generic feature couple with a customer specific configuration.

This separation is needed is order to have a good module worth
contributing. But it means some overhead work, and will often come as an
afterthought, especially if you didn't share the design in a Github
issue before contributing the code. Along with other issues, such as
monolithic/too large modules, are not trivial to solve, and can be a
significant barrier for contribution.

Inexperienced contributors need help from experienced ones to cut these
diamonds out of their stones. Once they also become experienced with the
OCA, they will learn to think about this since the initial design phase,
and make OCA inclusions almost painless.

A path for new contributions
============================

For modules created with the OCA in mind, the author is usually
experienced with the workflow and criteria. To start with, authors will
usually check for similar modules available, or under pull request
reviews, to avoid feature overlaps. Author may also create RFC Issues to
discuss upfront their idea and design with other contributors. This
makes the review and approval process easier.

Contributions coming from multiple sources
------------------------------------------

**For modules created outside the OCA, the process may be much harder,
and will frequently involve significant effort to bring to the OCA
standards**. Some are simpler, like passing code lint checks, adapting
code to OCA standards. Some might be troublesome, like changing the
module technical name to comply to naming standards, when it is already
deployed on customers with the current name. Others are more complex and
subtle, such as overlapping or incompatibility with existing OCA
modules, or having assumptions making it usable for fewer few cases.

**The difficult process of adapting pre-existing code to the OCA creates
frustration and can drive potential new contributors away from the
OCA.** When well intentioned people and companies, having decided to be
part and contribute to the OCA, generously propose some modules
previously built for their customers, they will often face the above
barriers. This creates frustration, and may even be perceived as some
hostility from the established contributors against new ones. It will be
easier to just give up, instead of trying to climb the steep path
towards the pull request approval.

**The introduction of Maturity Levels allows to lower the OCA criteria
for modules in Alpha and Beta stages, allowing for an easier entrance
for new contributors.** The modules in these stages are seen as a work
in progress towards the Stable and Mature stages, where all the OCA
criteria should be met. Allowing to step into the OCA codebase earlier
provides better motivation and confidence in the process, and to break
down the long adaptation work into several pull requests. It makes it
easier for other contributors to collaborate in that work, and for
experienced contributors to step in and help in the code transformations
needed.

Competing features
------------------

**As a general principle, the OCA is committed to provide one reference
solution for each feature.** From the development point of view, this
promotes to collaborate around the reference solution, to improve and
expand it, as opposed to having several solutions, each covering their
specific use case. For integrators and users, this spares them from the
work of comparing different OCA modules, and predicting which ones will
be actively maintained.

**But there are benefits in allowing alternative solutions to be
presented, developed, and to challenge the established one.** Sometimes
there are competing visions of what should be the reference
implementation for some feature.

These could be two pull requests competing to add a feature, a later
proposed solution that challenges the established one. The community
needs not be tied to a specific solution just because it was proposed
and accepted first.

While only one can be allowed for Stable/Mature level, accepting the
alternatives in Alpha/Beta levels provides the possibility for them to
gather contributions, evolve, and eventually becoming the reference for
the next Odoo major version..

**In case a challenger solution becomes the reference, a migration path
must be provided, honoring the user’s stability expectations.** This
should happen on new Odoo major versions. For example, on Odoo 11.0 the
stable module A is challenged by the beta module B. On Odoo 12.0 the
maintainers decide that B should now become the reference. Module B is
then promoted to Stable or Mature on branch 12.0, and will include
scripts to migrate from the 11.0 module A. At the same time module A
should be demoted to Beta in branch 12.0.

OCA repository organization
===========================

The OCA code repositories are first organized by topics of interest.
This allows for closely related modules to be tested together, and to
provide a common work space for people with the same interests. The
repository size is also relevant for the organization, since if too
large they can generate too much noise. So if size becomes an issue,
splitting some sub-topic(s) into their own repository is welcome.

Module maturity levels is not a factor when choosing the repository to
host modules. Regardless of the Maturity Level, modules will be hosted
on the same repositories. In some cases, an existing codebase can be
contributed to the OCA in a dedicated “beta repository”, if it comes
organised in a vertical-like repository. Its goal is to be a
collaboration workspace to gradually improve those modules and promote
them to the final repositories where they will be hosted.

The general organization of OCA code repositories is the following:

Main App Repositories
---------------------

Odoo features are provided by addon modules.

Some modules provide Applications, such as “Sales” or “Project”,
implementing the basic features for that app.

The other module provide additional features to Apps.

There should be one main repository for each App, containing extension
features for it. Every repository will have a PSC responsible for it,
and it should be clearly identified in the repository README.

Some repositories provide completely new Apps, nonexistent in the Odoo
core addons, such as management-system (support for multiple management
systems, including ISO9001), and privacy (support for data privacy and
protection , including GDPR compliance features).

So, in general, the modules in these repositories should be prefixed
with the App name, such as sale\_ or project\_. Exceptions can be
allowed by PSC decision.

Topic Repositories
------------------

In some cases, particular topics are extensive enough to deserve their
own repository.

This may be because the topic is specific enough to be interesting only
to a significant subset of contributors, or just because it it is large
enough to be worth a dedicated repository, reducing excessive traffic
from the main repository.

For example the Sales modules are spread across sale\_workflow,
sale\_financial and sale\_reporting repositories, and the Project
modules have the main project repository, and also the contract and the
project-agile topic specific repositories.

Vertical and Localization Repositories
--------------------------------------

A different case are repositories aiming to provide solutions tailored
to specific markets - business sectors or countries (legal requirements
and common practices).

These are distinct from Topic repositories in that they are typically
cross-functional, providing extensions to the several different
functional areas (core Apps), along with some specific modules, that
otherwise wouldn’t fit Main or Topic repositories.

In the long run, they should contain only the specific features needed.
Features also relevant for other use cases, outside the vertical’s
perimeter, should ideally be extracted and moved to the appropriate Main
or Topic repository.

For example, SEPA features (bank transactions in the Euro Area) are
relevant for the Localizations of several European countries. If a
Localization repository includes a SEPA feature, it should be aimed to
later be extracted and moved to a common Banking related repository.
Note that the maturity levels can be leveraged to do this gradually, so
this does not have to be a blocking issue to allow including the feature
right away.

Incubation Repositories
-----------------------

Another case is when a team wants to share a body of work with the OCA,
typically a full repository. This work was funded by end customers, and
the team is kindly contributing it to the OCA, which is positive and
should be well received.

It will often be a set of modules that work together to form a solution,
covering some features not in OCA repositories, and other features
overlapping with existing OCA ones.

Even with the feature overlapping issues, and the separation of features
between repositories, accepting this contribution earlier allows for
collaboration around them to gradually converge with the reference
repositories. Features can be gradually adapted or extracted from it,
until it is either empty, or if it is a minimal vertical-like
repository.

Workflow for contributed modules and repositories
-------------------------------------------------

Experienced OCA contributors will usually create new modules in the OCA
repositories, or in personal repositories but with OCA in mind since the
design stage.

Newcomers to OCA contributions will usually have codebases created for
their customers, that they are willing to propose to the OCA. These need
special consideration when proposed to the OCA, in order to provide
fruitful collaboration, and provide a journey that allow these modules
to fit the OCA existing codebase and reach OCA quality standards.

Repository Responsibilities [TODO]
----------------------------------

PSC responsibilities…

Maintainer definition and responsibilities…

Review Guidelines [TODO]
------------------------

At the feature curation level, review guidelines are needed to help
reviewers decide on the adequate maturity levels, and steps needed to
bring the module to the next maturity level.

.. note::
   The canonical URL to this document is https://odoo-community.org/page/repository-policy.
