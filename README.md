Ansible Selenium Setup
======================

> Ansible script that installs selenium and all the requirements for the popular webdrivers

This role is meant to be run locally. So see the [example playbook](#example-playbook) for how to do that.

Installation
------------

* `mkdir -p selenium-installation/roles`
* `cd selenium-installation`
* `touch playbook.yml`
* `git clone https://github.com/invokemedia/ansible-selenium-setup roles/invokemedia.selenium-setup`

Role Variables
--------------

```
# these ARE NOT browser versions! These are the versions of the drivers to download and install

# geck driver version
gecko_version: 0.17.0
# chrome driver version
chrome_version: 2.9
# safari driver version
safari_version: 2.48
# selenium driver version
selenium_version: 3.4.0
```

Dependencies
------------

None.

Example Playbook
-------------------------

Here is how you would use the default setup setup.

```
- hosts: 127.0.0.1
  connection: local
  gather_facts: no
  roles:
    - { role: invokemedia.selenium-setup }
```

Then use `ansible-playbook playbook.yml -i 'localhost,'` to play.

This will create a `selenium-server.jar` in `/usr/local/bin/` and also create a `/usr/local/bin/selenium` which is a script that you can use to simply launch the server.

License
-------

MIT

Author Information
------------------

* [Invoke Media](http://www.invokemedia.com/)
* <webmaster@invokemedia.com>

References
----------

* [james2doyle/selenium-instructions.md](https://gist.github.com/james2doyle/e41c01563f132bc6ce6409af12365a8b)
