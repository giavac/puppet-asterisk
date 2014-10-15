puppet-asterisk
===============

## Description

Puppet module for Asterisk


=======

Overview
--------

The asterisk module provides a simple interface for managing Asterisk deployments with Puppet.

Module Description
------------------

Asterisk is a free and open source framework for building communications applications
[http://www.asterisk.org/](http://www.asterisk.org/)
This module helps you installing and configuring Asterisk with Puppet.

Setup
-----

To install Asterisk with the default parameters:

    class { '::asterisk': }

(this will also install the default package version for the current distribution).

If you want a specific package version (must be available depending on apt sources configuration):

    class { '::asterisk':
        package_ensure => '<MY VERSION>',
    }

**On an empty host:**

    apt-get update && apt-get install -y puppet
    ## This will also pull puppetlabs-stdlib
    puppet module install trulabs-asterisk
    puppet apply -v /etc/puppet/modules/asterisk/tests/init.pp --show_diff --noop

Parameters
----------


#####`service_enable`

Enable Asterisk.

#####`service_ensure`

Ensure the service is running or stopped.

#####`service_manage`

Whether Puppet should manage Asterisk as a service.

#####`package_ensure`

What the asterisk package version should be (including present, latest, absent).

#####`package_name`

Name of the asterisk package.

#####`manage_config`

Take care of configuration files, or delegate to something else external.

#####`ast_dump_core`

Create core dumps ('no' is false, everything else true).

#####`rtpstart`

Lower limit for RTP port range.

#####`rtpend`

Upper limit for RTP port range.

#####`udpbindaddr`

Interface (with optional port) where to bind UDP.

#####`tcpenable`

Enable TCP ('yes' or 'no').

#####`tcpbindaddr`

Interface (with optional port) where to bind TCP.

#####`tlsenable`

Enable TLS ('yes' or 'no').

#####`tlsbindaddr`

Interface (with optional port) where to bind TLS.

#####`tlscertfile`

Path for TLS certificate.

#####`tlsprivatekey`

Path for TLS private key file.

#####`tlscafile`

Path for TLS CA file..

#####`tlscapath`

Path for TLS CA files folder.

#####`tlsdontverifyserver`

As TLS client, verify or not the server certificate ('yes' or 'no').


Author
------

    Truphone Labs
    Giacomo Vacca <giacomo.vacca@gmail.com>

License
-------

See LICENSE file.

##Limitations

This module has been built and tested with Puppet 2.7.

The module has been tested on:
* Debian 7

##Tests

Run tests with:
    sudo puppet apply -v tests/init.pp --modulepath modules/:/etc/puppet/modules --show_diff --noop

##Contributors
The list of contributors can be found at: [https://github.com/trulabs/puppet-asterisk/graphs/contributors](https://github.com/trulabs/puppet-asterisk/graphs/contributors)
