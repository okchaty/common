Ansible Role Common
###################

|Build Status| |Ansible Galaxy| |GitHub issues| |Average time to resolve an issue| |Percentage of issues still open| |GitHub license|

:Version: 0.3.1
:Web: https://github.com/okchaty/common
:Download: http://github.com/okchaty/common
:Source: http://github.com/okchaty/common
:Keywords: common

.. contents:: Table of Contents:
    :local:

Requirements:
=============

List of applications:

- `Python 3.6.1`_
- `Docker`_
- `Docker Compose`_

Install
=======

Install it with the following command:

.. code-block:: bash

    $ ansible-galaxy install okchaty.common

Role Variables
==============

The default role variables in ``defaults/main.yml`` are:

.. code-block:: yaml

    common_pip_packages:
        - name: celery
        version: 4.0.2

.. code-block:: yaml

    common_packages:
        - python
        - git

-  Env Vars:

.. code-block:: yaml

    common_env_vars:
        var1:value 1
        var2:value 2

- user:

.. code-block:: yaml

    common_user: ubuntu

- Deploy code

.. code-block:: yaml

    common_only_deploy: yes

Dependencies
============

None

Example Playbook
================

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

        - hosts: servers
          roles:
            - okchaty.common

To install a specific version:

.. code:: yaml

      - hosts: servers
        roles:
          - { role: okchaty.common }

.. code:: yaml

        - hosts: servers
          roles:
             - role: okchaty.common
                common_package_dependencies:
                - vim

Add: users to group:

.. code:: yaml

        - hosts: servers
          roles:
             - role: okchaty.common
                common_users:
                - user: test
                  group: test-group

Add: files to server:

.. code:: yaml

    common_user = "{{ user}}"
    common_copy_files:
      - src: /usr/src/file
        path: /usr/src/server/file
        permissions: 0640


License
=======

MIT

Changelog
=========

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
============

Please see `CONTRIBUTING`_ for details.

Credits
=======

-  `author`_
-  `contributors`_

Made with :heart: :coffee: and :pizza: by `author`_ and `company`_.

.. Badges:

.. |Build Status| image:: https://travis-ci.org/okchaty/common.svg
   :target: https://travis-ci.org/okchaty/common
.. |Ansible Galaxy| image:: https://img.shields.io/badge/galaxy-okchaty.common-blue.svg
   :target: https://galaxy.ansible.com/okchaty/common/
.. |GitHub issues| image:: https://img.shields.io/github/issues/okchaty/common.svg
   :target: https://github.com/okchaty/common/issues
.. |Average time to resolve an issue| image:: http://isitmaintained.com/badge/resolution/okchaty/common.svg
   :target: http://isitmaintained.com/project/okchaty/common
.. |Percentage of issues still open| image:: http://isitmaintained.com/badge/open/okchaty/common.svg
   :target: http://isitmaintained.com/project/okchaty/common
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
   :target: LICENSE

.. Links
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: AUTHORS
.. _`contributing`: CONTRIBUTING.rst

.. _`company`: https://github.com/okchaty
.. _`author`: https://github.com/luismayta

.. dependences
.. _Python 3.6.1: https://www.python.org/downloads/release/python-361
.. _Docker: https://www.docker.com/
.. _Docker Compose: https://docs.docker.com/compose/