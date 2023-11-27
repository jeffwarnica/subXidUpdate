Role Name
=========

Quick and dirty role to update /etc/sub[ug]id files.

Will update `/etc/subuid`, `/etc/subgid` given `uid` and `gid` to add the user and group to subuid/subgid files.

Can update only one of the files with `files`.
Can use custom size with `subxid_size`.
Can choose to fail or ignore if an entry matching the id exists.

Does *not* have the ability to update the start or length of an entiry.

Requirements
------------

A computer, I suppose. Does not support cardboard or cardboard derivatives.

Role Variables
--------------

| var | default | notes |
| --- | ------- | ----- |
| uid | none    | required |
| files | both | 'uid' 'gid' or 'both' |
| subuid_file | /etc/subuid |
| subgid_file | /etc/subgid |
| subxid_size | 65536 |
| found_strategy | fail | or skip

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

 ....
  tasks:
    - name: Add bob to subXid files
      ansible.builtin.include_role:
        name: subXidUpdate
      vars:
        subuid_file: tmp/subuid
        subgid_file: tmp/subgid
        subxid_size: 65536
        uid: bob
        gid: bobgroup
        found_strategy: skip
        files: both

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
