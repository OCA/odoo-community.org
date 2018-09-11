##################################
|TITLE| (|DATE|)
##################################

.. |TITLE| replace:: OCA Module Lifecycle - Maintainer Role Policy
.. |DATE| replace:: 2018/08/24

.. fill in the Document information in the above lines. It will be automatically
   replaced in the document header. Don't forget to remove the []

.. contents:: Table of contents
    :depth: 4

.. sectnum::

Introduction
============
A Maintainer is responsible to ensure the coordination of specific addon
modules in order to ensure the quality and consistency of the
contributions. For a particular repository, this could be one, a few, or
even all the modules in that repository.

Typically, the maintainer role for OCA repositories is expected to be
done by the Project Steering Committee (PSC) members. `*Project Steering
Committees* <https://odoo-community.org/page/oca-project-steering-committee-guide>`__
are defined by the `OCA
Bylaws, <https://odoo-community.org/page/Bylaws>`__ section V.c). From
an Association perspective their main role is project oversight, and one
PSC can be responsible for one or more project repositories.

In large repositories it is sometimes difficult to identify who are the
active maintainers of a given addon. This creates the following
problems:

-  the maintainer does not easily notice PR and Issues concerning
       his/her addons;

-  when addons have no active maintainers, PSC members must take care of
       it, but they may be too busy or may not feel concerned by all
       addons in their repositories;

-  it is difficult for contributors to detect addons which have no
       active maintainer.

In small, focused repositories (eg management-system, operating-unit,
business-requirement, mis-builder, ...), this issue does not arise since
the repo maintainers and addons maintainers are the same.

In larger repos (server-tools, stock-logistics-\*, financial-tools,
bank-payment, ...), it happens that some or all PSC members are not
interested in all addons and the repo suffers of the above drawbacks,
therefore giving a negative impression on the whole repo.

Splitting large repositories so they all become focused with a
homogeneous content seems to be impractical, due to the difficulty to
manage a large amount of repositories.

The maintainer role has been introduced to alleviate the above issues.

Being the maintainer of an addon module bears some responsibilities
towards the community. This document aims at clarifying those.

Maintainer role and responsibilities
====================================

-  Maintainers main role is to foster efficient community collaboration
       on the addons they are responsible for. This includes

   -  **Communication:** Ensuring that discussions and reviews don’t
          stall, intervening to ping the people involved, or ask for
          next steps whenever communication stops.

   -  **Control:** Doing final checks and merging approved pull
          requests.

   -  **Versioning: **

      -  Bumping version numbers during merge or immediately after.

      -  For Mature addons, maintaining the recommended changelog
             (HISTORY.rst).

   -  **Support:** Handling support requests and questions.

   -  **Documentation:** Documenting and managing the roadmap (future
          improvement ideas, known issues).

   -  **Guidance:** Keeping an eye on contributions in related areas to
          help ensure functional consistency in OCA. This may include
          helping to merge new feature in the addons they maintain, or
          guiding contributors towards the creation of new extension
          modules. This must not preclude the creation of addons
          providing a competing approach, fostering innovation.

-  Declared maintainers are given write access to the repository. If
       they are not PSC member they are trusted not to do write
       operations (eg merging pull requests) that have impact on other
       addons than the one they maintain.

-  Maintainers may proceed to some maintenance operation with relaxed
       code review rules (eg performing simple, low risk, forward and
       backports, maintaining documentation, applying cosmetic
       improvements to the code such as linting). Maintainers are
       expected to follow the highest quality standard when performing
       such operations.

-  If there is more than one declared maintainer, they must ensure good
       coordination between them (for instance, ensure no task are left
       unattended on the assumption that another maintainer will do it).

-  PSC members should not merge PR concerning modules with declared
       maintainers, unless the maintainer is unreactive.

-  Addons with no declared maintainers are managed by the PSC.

Adding, removing maintainers
============================

-  The maintainers of an addon are declared in the **maintainers** key
       of the manifest. This key is a list of github logins. The list of
       declared maintainers is expected to be short (one or two in
       general).

-  New candidate maintainers can propose themselves by adding their
       github login in the manifest, with a PR, to be approved by the
       PSC.

-  Maintainers who do not wish to continue maintaining a module must
       remove themselves from the list through a PR, and announce it on
       the contributors mailing list, calling for volunteers.

-  PSC may remove maintainers who do not follow OCA rules or fail to
       their maintenance duties. Such action must be taken in
       coordination with the board.

-  Current maintainers are displayed (using their avatar) in the addon
       README.rst.

.. note::
   The canonical URL to this document is https://odoo-community.org/page/maintainer-role.
