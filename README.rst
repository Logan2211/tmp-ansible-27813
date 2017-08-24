Testing for ansible issue #27813
################################

Ansible playbooks to demonstrate the request in #27813.

.. image:: https://travis-ci.org/Logan2211/tmp-ansible-27813.svg?branch=master
    :target: https://travis-ci.org/Logan2211/tmp-ansible-27813

currentbehavior
===============

The ``playbook.yml`` shows that playbook handlers are inserted
in the handler scheduling after role handlers with no way to influence this
ordering at the playbook level.

workaround
==========

Uses a role executed multiple times to work around the inability to implement
the handler at the playbook level by using a small role with a listener to
do the LB orchestration.

featurereq
==========

Demonstrates that the "listen" attribute cannot accept dynamic Jinja2 templated
variables.

featurereq2
===========

A playbook to demonstrate what I'm asking in the issue #27813. I'd like to be
able to insert handlers at the playbook level as "pre_handlers"
and "post_handlers" which allow the playbook to specify the scheduling order
for the handlers in the blocks as before or after the current handler lists
implemented in Ansible.
