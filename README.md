# Empty meta yaml triggers "TypeError: argument of type 'NoneType' is not iterable"

[Empty meta yaml triggers &quot;TypeError: argument of type 'NoneType' is not iterable&quot; · Issue #1703 · ansible/ansible-lint](https://github.com/ansible/ansible-lint/issues/1703)

> Verify first that your issue is not already reported on GitHub

Similar to #1021 but the error message is iterable instead of subscriptable

> Also test if the latest release and main branch are affected too

Successfully reproduced on 5.1.2, not sure how to test the main branch using pipx installation, though

##### Summary

Supplying an empty meta/main.yml triggers a TypeError crash, refer the reproduce instructions for example.

##### Issue Type

- Bug Report

##### Ansible and Ansible Lint details
<!--- Paste verbatim output between triple backticks -->
```console (paste below)
ansible --version
ansible [core 2.11.4] 
  config file = /home/brlin/__REDACTED__/ansible.cfg
  configured module search path = ['/home/brlin/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /home/brlin/.local/pipx/venvs/ansible/lib/python3.9/site-packages/ansible
  ansible collection location = /home/brlin/.ansible/collections:/usr/share/ansible/collections
  executable location = /home/brlin/.local/bin/ansible
  python version = 3.9.5 (default, May 11 2021, 08:20:37) [GCC 10.3.0]
  jinja version = 3.0.1
  libyaml = True

ansible-lint --version
ansible-lint 5.1.2 using ansible 2.11.4

```

- ansible installation method: one of source, pip, OS package: pipx (based on pip)
- ansible-lint installation method: one of source, pip, OS package: pipx (based on pip)

##### OS / ENVIRONMENT
<!--- Provide all relevant information below, e.g. target OS versions, network device firmware, etc. -->

Ubuntu 21.04  
Python 3.9.5


##### STEPS TO REPRODUCE

```commands
git clone https://github.com/Lin-Buo-Ren/ansible-lint-bug-repro-empty-meta.git
cd ansible-lint-bug-repro-empty-meta
ansible-lint
```

##### Desired Behaviour

Program not crashed, possibly giving linting errors regarding the improper meta file

##### Actual Behaviour

<!--- Paste verbatim command output between triple backticks -->
```paste below
$ ansible-lint
Traceback (most recent call last):
  File "/home/brlin/.local/bin/ansible-lint", line 8, in <module>
    sys.exit(_run_cli_entrypoint())
  File "/home/brlin/.local/pipx/venvs/ansible-lint/lib/python3.9/site-packages/ansiblelint/__main__.py", line 299, in _run_cli_entrypoint
    sys.exit(main(sys.argv))
  File "/home/brlin/.local/pipx/venvs/ansible-lint/lib/python3.9/site-packages/ansiblelint/__main__.py", line 206, in main
    prepare_environment()
  File "/home/brlin/.local/pipx/venvs/ansible-lint/lib/python3.9/site-packages/ansiblelint/prerun.py", line 211, in prepare_environment
    _install_galaxy_role()
  File "/home/brlin/.local/pipx/venvs/ansible-lint/lib/python3.9/site-packages/ansiblelint/prerun.py", line 253, in _install_galaxy_role
    if 'galaxy_info' not in yaml:
TypeError: argument of type 'NoneType' is not iterable

```
