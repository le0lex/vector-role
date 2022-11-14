Traceback (most recent call last):
  File "/usr/local/bin/molecule", line 8, in <module>
    sys.exit(main())
  File "/usr/local/lib/python3.8/dist-packages/click/core.py", line 1130, in __call__
    return self.main(*args, **kwargs)
  File "/usr/local/lib/python3.8/dist-packages/click/core.py", line 1055, in main
    rv = self.invoke(ctx)
  File "/usr/local/lib/python3.8/dist-packages/click/core.py", line 1657, in invoke
    return _process_result(sub_ctx.command.invoke(sub_ctx))
  File "/usr/local/lib/python3.8/dist-packages/click/core.py", line 1404, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/usr/local/lib/python3.8/dist-packages/click/core.py", line 760, in invoke
    return __callback(*args, **kwargs)
  File "/usr/local/lib/python3.8/dist-packages/click/decorators.py", line 26, in new_func
    return f(get_current_context(), *args, **kwargs)
  File "/usr/local/lib/python3.8/dist-packages/molecule/command/test.py", line 176, in test
    base.execute_cmdline_scenarios(scenario_name, args, command_args, ansible_args)
  File "/usr/local/lib/python3.8/dist-packages/molecule/command/base.py", line 112, in execute_cmdline_scenarios
    scenario.config.runtime.prepare_environment(
  File "/usr/local/lib/python3.8/dist-packages/ansible_compat/runtime.py", line 397, in prepare_environment
    self._install_galaxy_role(
  File "/usr/local/lib/python3.8/dist-packages/ansible_compat/runtime.py", line 557, in _install_galaxy_role
    raise InvalidPrerequisiteError(msg)
ansible_compat.errors.InvalidPrerequisiteError: Computed fully qualified role name of vector-role does not follow current galaxy requirements.
Please edit meta/main.yml and assure we can correctly determine full role name:

galaxy_info:
role_name: my_name  # if absent directory name hosting role is used instead
namespace: my_galaxy_namespace  # if absent, author is used instead

Namespace: https://galaxy.ansible.com/docs/contributing/namespaces.html#galaxy-namespace-limitations
Role: https://galaxy.ansible.com/docs/contributing/creating_role.html#role-names

As an alternative, you can add 'role-name' to either skip_list or warn_list.


PLAY [Destroy] ****************************************************************************************************************

TASK [Set async_dir for HOME env] *********************************************************************************************
[1;35m[WARNING]: Skipping plugin (/usr/lib/python3/dist-packages/ansible/plugins/filter/core.py) as it seems to be invalid: cannot[0m
[1;35mimport name 'environmentfilter' from 'jinja2.filters' (/usr/local/lib/python3.8/dist-packages/jinja2/filters.py)[0m
[1;35m[WARNING]: Skipping plugin (/usr/lib/python3/dist-packages/ansible/plugins/filter/mathstuff.py) as it seems to be invalid:[0m
[1;35mcannot import name 'environmentfilter' from 'jinja2.filters' (/usr/local/lib/python3.8/dist-packages/jinja2/filters.py)[0m
[31mfatal: [localhost]: FAILED! => {"censored": "the output has been hidden due to the fact that 'no_log: true' was specified for this result"}[0m

PLAY RECAP ********************************************************************************************************************
[31mlocalhost[0m                  : ok=0    changed=0    unreachable=0    [31mfailed=1   [0m skipped=0    rescued=0    ignored=0



PLAY [Destroy] ****************************************************************************************************************

TASK [Set async_dir for HOME env] *********************************************************************************************
[1;35m[WARNING]: Skipping plugin (/usr/lib/python3/dist-packages/ansible/plugins/filter/core.py) as it seems to be invalid: cannot[0m
[1;35mimport name 'environmentfilter' from 'jinja2.filters' (/usr/local/lib/python3.8/dist-packages/jinja2/filters.py)[0m
[1;35m[WARNING]: Skipping plugin (/usr/lib/python3/dist-packages/ansible/plugins/filter/mathstuff.py) as it seems to be invalid:[0m
[1;35mcannot import name 'environmentfilter' from 'jinja2.filters' (/usr/local/lib/python3.8/dist-packages/jinja2/filters.py)[0m
[31mfatal: [localhost]: FAILED! => {"censored": "the output has been hidden due to the fact that 'no_log: true' was specified for this result"}[0m

PLAY RECAP ********************************************************************************************************************
[31mlocalhost[0m                  : ok=0    changed=0    unreachable=0    [31mfailed=1   [0m skipped=0    rescued=0    ignored=0



PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
[32mok: [localhost][0m

TASK [Destroy molecule instance(s)] ********************************************
[33mchanged: [localhost] => (item=centos_7)[0m
[33mchanged: [localhost] => (item=centos_8)[0m
[33mchanged: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Wait for instance(s) deletion to complete] *******************************
[32mok: [localhost] => (item=centos_7)[0m
[32mok: [localhost] => (item=centos_8)[0m
[32mok: [localhost] => (item=ubuntu)[0m
[32mok: [localhost] => (item=instance)[0m

TASK [Delete docker networks(s)] ***********************************************

PLAY RECAP *********************************************************************
[33mlocalhost[0m                  : [32mok=3   [0m [33mchanged=1   [0m unreachable=0    failed=0    [36mskipped=1   [0m rescued=0    ignored=0


playbook: /home/leolex/SW/pycharm-community-2021.3.3/my_git01/ansible/playbook_8.5/roles/vectorrole/molecule/default/converge.yml

PLAY [Create] ******************************************************************

TASK [Set async_dir for HOME env] **********************************************
[32mok: [localhost][0m

TASK [Log into a Docker registry] **********************************************
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost][0m

TASK [Check presence of custom Dockerfiles] ************************************
[32mok: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})[0m

TASK [Create Dockerfiles from image names] *************************************
[36mskipping: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}) [0m

TASK [Synchronization the context] *********************************************
[36mskipping: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}) [0m

TASK [Discover local Docker images] ********************************************
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 0, 'ansible_index_var': 'i'})[0m
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 1, 'ansible_index_var': 'i'})[0m
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 2, 'ansible_index_var': 'i'})[0m
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 3, 'ansible_index_var': 'i'})[0m

TASK [Build an Ansible compatible image (new)] *********************************
[36mskipping: [localhost] => (item=molecule_local/centos:7) [0m
[36mskipping: [localhost] => (item=molecule_local/centos:8_update) [0m
[36mskipping: [localhost] => (item=molecule_local/ubuntu:python) [0m
[36mskipping: [localhost] => (item=molecule_local/quay.io/centos/centos:stream8) [0m

TASK [Create docker network(s)] ************************************************

TASK [Determine the CMD directives] ********************************************
[32mok: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})[0m

TASK [Create molecule instance(s)] *********************************************
[33mchanged: [localhost] => (item=centos_7)[0m
[33mchanged: [localhost] => (item=centos_8)[0m
[33mchanged: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Wait for instance(s) creation to complete] *******************************
[33mchanged: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '330149708942.3793', 'results_file': '/home/leolex/.ansible_async/330149708942.3793', 'changed': True, 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item'})[0m
[1;30mFAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (300 retries left).[0m
[31mfailed: [localhost] (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '316134481162.3821', 'results_file': '/home/leolex/.ansible_async/316134481162.3821', 'changed': True, 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item'}) => {"ansible_job_id": "316134481162.3821", "ansible_loop_var": "item", "attempts": 2, "changed": false, "finished": 1, "item": {"ansible_job_id": "316134481162.3821", "ansible_loop_var": "item", "changed": true, "failed": 0, "finished": 0, "item": {"image": "centos:8_update", "name": "centos_8", "pre_build_image": true}, "results_file": "/home/leolex/.ansible_async/316134481162.3821", "started": 1}, "msg": "Error pulling image centos:8_update - 404 Client Error for http+docker://localhost/v1.41/images/create?tag=8_update&fromImage=centos: Not Found (\"manifest for centos:8_update not found: manifest unknown: manifest unknown\")", "results_file": "/home/leolex/.ansible_async/316134481162.3821", "started": 1, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}[0m
[31mfailed: [localhost] (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '626378555255.3848', 'results_file': '/home/leolex/.ansible_async/626378555255.3848', 'changed': True, 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item'}) => {"ansible_job_id": "626378555255.3848", "ansible_loop_var": "item", "attempts": 1, "changed": false, "finished": 1, "item": {"ansible_job_id": "626378555255.3848", "ansible_loop_var": "item", "changed": true, "failed": 0, "finished": 0, "item": {"image": "ubuntu:python", "name": "ubuntu", "pre_build_image": true}, "results_file": "/home/leolex/.ansible_async/626378555255.3848", "started": 1}, "msg": "Error pulling image ubuntu:python - 404 Client Error for http+docker://localhost/v1.41/images/create?tag=python&fromImage=ubuntu: Not Found (\"manifest for ubuntu:python not found: manifest unknown: manifest unknown\")", "results_file": "/home/leolex/.ansible_async/626378555255.3848", "started": 1, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}[0m
[1;30mFAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (300 retries left).[0m
[1;30mFAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (299 retries left).[0m
[1;30mFAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (298 retries left).[0m
[1;30mFAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (297 retries left).[0m
[33mchanged: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '995913332409.3971', 'results_file': '/home/leolex/.ansible_async/995913332409.3971', 'changed': True, 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})[0m

PLAY RECAP *********************************************************************
[31mlocalhost[0m                  : [32mok=5   [0m [33mchanged=1   [0m unreachable=0    [31mfailed=1   [0m [36mskipped=5   [0m rescued=0    ignored=0


PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
[32mok: [localhost][0m

TASK [Destroy molecule instance(s)] ********************************************
[33mchanged: [localhost] => (item=centos_7)[0m
[33mchanged: [localhost] => (item=centos_8)[0m
[33mchanged: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Wait for instance(s) deletion to complete] *******************************
[33mchanged: [localhost] => (item=centos_7)[0m
[32mok: [localhost] => (item=centos_8)[0m
[32mok: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Delete docker networks(s)] ***********************************************

PLAY RECAP *********************************************************************
[33mlocalhost[0m                  : [32mok=3   [0m [33mchanged=2   [0m unreachable=0    failed=0    [36mskipped=1   [0m rescued=0    ignored=0


PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
[32mok: [localhost][0m

TASK [Destroy molecule instance(s)] ********************************************
[33mchanged: [localhost] => (item=centos_7)[0m
[33mchanged: [localhost] => (item=centos_8)[0m
[33mchanged: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Wait for instance(s) deletion to complete] *******************************
[32mok: [localhost] => (item=centos_7)[0m
[32mok: [localhost] => (item=centos_8)[0m
[32mok: [localhost] => (item=ubuntu)[0m
[32mok: [localhost] => (item=instance)[0m

TASK [Delete docker networks(s)] ***********************************************

PLAY RECAP *********************************************************************
[33mlocalhost[0m                  : [32mok=3   [0m [33mchanged=1   [0m unreachable=0    failed=0    [36mskipped=1   [0m rescued=0    ignored=0


playbook: /home/leolex/SW/pycharm-community-2021.3.3/my_git01/ansible/playbook_8.5/roles/vectorrole/molecule/default/converge.yml

PLAY [Create] ******************************************************************

TASK [Set async_dir for HOME env] **********************************************
[32mok: [localhost][0m

TASK [Log into a Docker registry] **********************************************
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost] => (item=None) [0m
[36mskipping: [localhost][0m

TASK [Check presence of custom Dockerfiles] ************************************
[32mok: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})[0m

TASK [Create Dockerfiles from image names] *************************************
[36mskipping: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}) [0m

TASK [Synchronization the context] *********************************************
[36mskipping: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}) [0m
[36mskipping: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}) [0m

TASK [Discover local Docker images] ********************************************
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 0, 'ansible_index_var': 'i'})[0m
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 1, 'ansible_index_var': 'i'})[0m
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 2, 'ansible_index_var': 'i'})[0m
[32mok: [localhost] => (item={'changed': False, 'skipped': True, 'skip_reason': 'Conditional result was False', 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item', 'i': 3, 'ansible_index_var': 'i'})[0m

TASK [Build an Ansible compatible image (new)] *********************************
[36mskipping: [localhost] => (item=molecule_local/centos:7) [0m
[36mskipping: [localhost] => (item=molecule_local/centos:8_update) [0m
[36mskipping: [localhost] => (item=molecule_local/ubuntu:python) [0m
[36mskipping: [localhost] => (item=molecule_local/quay.io/centos/centos:stream8) [0m

TASK [Create docker network(s)] ************************************************

TASK [Determine the CMD directives] ********************************************
[32mok: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})[0m
[32mok: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})[0m

TASK [Create molecule instance(s)] *********************************************
[33mchanged: [localhost] => (item=centos_7)[0m
[33mchanged: [localhost] => (item=centos_8)[0m
[33mchanged: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Wait for instance(s) creation to complete] *******************************
[33mchanged: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '322071493121.5359', 'results_file': '/home/leolex/.ansible_async/322071493121.5359', 'changed': True, 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item'})[0m
[1;30mFAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (300 retries left).[0m
[31mfailed: [localhost] (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '783091234460.5387', 'results_file': '/home/leolex/.ansible_async/783091234460.5387', 'changed': True, 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item'}) => {"ansible_job_id": "783091234460.5387", "ansible_loop_var": "item", "attempts": 2, "changed": false, "finished": 1, "item": {"ansible_job_id": "783091234460.5387", "ansible_loop_var": "item", "changed": true, "failed": 0, "finished": 0, "item": {"image": "centos:8_update", "name": "centos_8", "pre_build_image": true}, "results_file": "/home/leolex/.ansible_async/783091234460.5387", "started": 1}, "msg": "Error pulling image centos:8_update - 404 Client Error for http+docker://localhost/v1.41/images/create?tag=8_update&fromImage=centos: Not Found (\"manifest for centos:8_update not found: manifest unknown: manifest unknown\")", "results_file": "/home/leolex/.ansible_async/783091234460.5387", "started": 1, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}[0m
[31mfailed: [localhost] (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '900448428974.5420', 'results_file': '/home/leolex/.ansible_async/900448428974.5420', 'changed': True, 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item'}) => {"ansible_job_id": "900448428974.5420", "ansible_loop_var": "item", "attempts": 1, "changed": false, "finished": 1, "item": {"ansible_job_id": "900448428974.5420", "ansible_loop_var": "item", "changed": true, "failed": 0, "finished": 0, "item": {"image": "ubuntu:python", "name": "ubuntu", "pre_build_image": true}, "results_file": "/home/leolex/.ansible_async/900448428974.5420", "started": 1}, "msg": "Error pulling image ubuntu:python - 404 Client Error for http+docker://localhost/v1.41/images/create?tag=python&fromImage=ubuntu: Not Found (\"manifest for ubuntu:python not found: manifest unknown: manifest unknown\")", "results_file": "/home/leolex/.ansible_async/900448428974.5420", "started": 1, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}[0m
[33mchanged: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '68881954232.5535', 'results_file': '/home/leolex/.ansible_async/68881954232.5535', 'changed': True, 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})[0m

PLAY RECAP *********************************************************************
[31mlocalhost[0m                  : [32mok=5   [0m [33mchanged=1   [0m unreachable=0    [31mfailed=1   [0m [36mskipped=5   [0m rescued=0    ignored=0


PLAY [Destroy] *****************************************************************

TASK [Set async_dir for HOME env] **********************************************
[32mok: [localhost][0m

TASK [Destroy molecule instance(s)] ********************************************
[33mchanged: [localhost] => (item=centos_7)[0m
[33mchanged: [localhost] => (item=centos_8)[0m
[33mchanged: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Wait for instance(s) deletion to complete] *******************************
[33mchanged: [localhost] => (item=centos_7)[0m
[32mok: [localhost] => (item=centos_8)[0m
[32mok: [localhost] => (item=ubuntu)[0m
[33mchanged: [localhost] => (item=instance)[0m

TASK [Delete docker networks(s)] ***********************************************

PLAY RECAP *********************************************************************
[33mlocalhost[0m                  : [32mok=3   [0m [33mchanged=2   [0m unreachable=0    failed=0    [36mskipped=1   [0m rescued=0    ignored=0

