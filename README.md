# Empty meta yaml triggeres "TypeError: argument of type 'NoneType' is not iterable"

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
<!--- Describe exactly how to reproduce the problem, using a minimal test-case -->

<!--- Paste example playbooks or commands between triple backticks below -->
```console (paste below)

```

<!--- HINT: You can paste gist.github.com links for larger files -->

##### Desired Behaviour
<!--- Describe what you expected to happen when running the steps above -->

Possible security bugs should be reported via email to `security@ansible.com`

##### Actual Behaviour
<!--- Describe what actually happened. If possible run with extra verbosity (-vvvv) -->

Please give some details of what is actually happening.
Include a [minimum complete verifiable example] with:
- playbook
- output of running ansible-lint
- if you're getting a stack trace, output of
  `ansible-playbook --syntax-check playbook`


<!--- Paste verbatim command output between triple backticks -->
```paste below

```


[minimum complete verifiable example]: http://stackoverflow.com/help/mcve
