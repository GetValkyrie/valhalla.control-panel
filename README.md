# Ansible Role: Valhalla

[![Build Status](https://travis-ci.org/GetValkyrie/ansible-role-valhalla.svg?branch=master)](https://travis-ci.org/GetValkyrie/ansible-role-valhalla)

Installs Aegir and various extensions to provide a deployment target for sites
developed on Valkyrie. Valhalla is intended to run on cloud infrastructure, and
currently supports AWS. For example, the current deployment model is a cluster
of front-end web nodes with files hosted on S3, behind Varnish caches and an
ElasticLoadBalancer, with RDS databases, ElastiCache Redis, etc.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):


## Dependencies

  - getvalkyrie.aegir (Installs Aegir).
  - getvalkyrie.skynet (Installs the Skynet queue for Aegir).

## Example Playbook

    - hosts: servers
      roles:
        - { role: getvalkyrie.valhalla }

After the playbook runs, the Aegir front-end site will be available, as will
the Drush extensions (Provision, et. al.) that do the heavy lifting. In
addition, hosting_s3 will be deployed, to allow provisioning of S3 buckets
during site installs.

## License

MIT / BSD

## Author Information

This role was created in 2015 by [Christopher Gervais](http://ergonlogic.com/), lead maintainer of the [Aegir Hosting System](http://www.aegirproject.org).
