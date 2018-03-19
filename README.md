Drone
=========

* Install and configure [Drone.io Continuous integration server](http://docs.drone.io/).

* Users listed in `drone_admins` will have admin rights on the Drone server.

* Users listed in `drone_users` will be granted access to the Drone CI UI.

* The `drone_role` variable can be used to deploy either the `server` or the `agent` or both of them if set to all `all`.


Requirements
------------

**:wave: IMPORTANT**

> In order to run this automation you first need to create a new OAuth consumer that will allow Drone to authenticate with Bitbucket.

* Bitbucket:

> To do so, go to [Bitbucket > Teams > <TeamName> > Settings > OAuth > Add consumer](https://bitbucket.org/account/user/). Once you get the OAuth client and secret, override in the proper group_vars the following variables in a vaulted file: `drone_bitbucket_client`, `drone_bitbucket_secret`

> As the `drone cli` requires a personal token to manage non admin users, the playbook will prompt for it at the right time. You can retrieve a Drone personal access token from your user profile screen. Click the show token button.
![Drone User Token](http://docs.drone.io/images/drone_user_token.png)

> Once you have an admin token generated you can add it to the vault file for the variable `drone_cli_token`: `<personal-token>`. If set the playbook wont prompt for it and use it from `group_vars`.

* Github:


Role Variables
--------------

TODO

Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: Lowess.drone }

License
-------

BSD

Author Information
------------------

This role was created in 2018 by [Florian Dambrine](http://floriandambrine.com/), used in [DevOps-360 Automation](http://slides.com/floriandambrine/devops360) course.
