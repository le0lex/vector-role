[root@b6a0e640e920 vector-role]# tox
py37-ansible210 installed: ansible==2.10.7,ansible-base==2.10.17,ansible-compat==1.0.0,ansible-lint==5.1.3,arrow==1.2.3,bcrypt==4.0.1,binaryornot==0.4.4,bracex==2.3.post1,cached-property==1.5.2,Cerberus==1.3.2,certifi==2022.9.24,cffi==1.15.1,chardet==5.0.0,charset-normalizer==2.1.1,click==8.1.3,click-help-colors==0.9.1,commonmark==0.9.1,cookiecutter==2.1.1,cryptography==38.0.3,distro==1.8.0,enrich==1.2.7,idna==3.4,importlib-metadata==5.0.0,Jinja2==3.1.2,jinja2-time==0.2.0,jmespath==1.0.1,lxml==4.9.1,MarkupSafe==2.1.1,molecule==3.4.0,molecule-podman==1.0.1,packaging==21.3,paramiko==2.12.0,pathspec==0.10.2,pluggy==0.13.1,pycparser==2.21,Pygments==2.13.0,PyNaCl==1.5.0,pyparsing==3.0.9,python-dateutil==2.8.2,python-slugify==6.1.2,PyYAML==5.4.1,requests==2.28.1,rich==12.6.0,ruamel.yaml==0.17.21,ruamel.yaml.clib==0.2.7,selinux==0.2.1,six==1.16.0,subprocess-tee==0.3.5,tenacity==8.1.0,text-unidecode==1.3,typing_extensions==4.4.0,urllib3==1.26.12,wcmatch==8.4.1,yamllint==1.26.3,zipp==3.10.0
py37-ansible210 run-test-pre: PYTHONHASHSEED='4135157876'
py37-ansible210 run-test: commands[0] | molecule test -s default --destroy always
INFO     default scenario test matrix: dependency, lint, cleanup, destroy, syntax, create, prepare, converge, idempotence, side_effect, verify, cleanup, destroy
INFO     Performing prerun...
WARNING  Failed to locate command: [Errno 2] No such file or directory: 'git': 'git'
INFO     Guessed /opt/vector-role as project root directory
INFO     Using /root/.cache/ansible-lint/b984a4/roles/leolex.vectorrole symlink to current repository in order to enable Ansible to find the role using its expected full name.
INFO     Added ANSIBLE_ROLES_PATH=~/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles:/root/.cache/ansible-lint/b984a4/roles
INFO     Running default > dependency
INFO     Running ansible-galaxy collection install --force -v containers.podman:>=1.7.0
INFO     Running ansible-galaxy collection install --force -v ansible.posix:>=1.3.0
WARNING  Skipping, missing the requirements file.
WARNING  Skipping, missing the requirements file.
INFO     Running default > lint
INFO     Lint is disabled.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy
INFO     Sanity checks: 'podman'

PLAY [Destroy] *****************************************************************

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})

TASK [Wait for instance(s) deletion to complete] *******************************
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '523339098005.93', 'results_file': '/root/.ansible_async/523339098005.93', 'changed': True, 'failed': False, 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '92407598910.113', 'results_file': '/root/.ansible_async/92407598910.113', 'changed': True, 'failed': False, 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '224175048925.145', 'results_file': '/root/.ansible_async/224175048925.145', 'changed': True, 'failed': False, 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '330155583848.176', 'results_file': '/root/.ansible_async/330155583848.176', 'changed': True, 'failed': False, 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     Running default > syntax

playbook: /opt/vector-role/molecule/default/converge.yml
INFO     Running default > create

PLAY [Create] ******************************************************************

TASK [get podman executable path] **********************************************
ok: [localhost]

TASK [save path to executable as fact] *****************************************
ok: [localhost]

TASK [Log into a container registry] *******************************************
skipping: [localhost] => (item="centos_7 registry username: None specified") 
skipping: [localhost] => (item="centos_8 registry username: None specified") 
skipping: [localhost] => (item="ubuntu registry username: None specified") 
skipping: [localhost] => (item="instance registry username: None specified") 

TASK [Check presence of custom Dockerfiles] ************************************
ok: [localhost] => (item=Dockerfile: None specified)
ok: [localhost] => (item=Dockerfile: None specified)
ok: [localhost] => (item=Dockerfile: None specified)
ok: [localhost] => (item=Dockerfile: None specified)

TASK [Create Dockerfiles from image names] *************************************
skipping: [localhost] => (item="Dockerfile: None specified; Image: centos:7") 
skipping: [localhost] => (item="Dockerfile: None specified; Image: centos:8_update") 
skipping: [localhost] => (item="Dockerfile: None specified; Image: ubuntu:python") 
skipping: [localhost] => (item="Dockerfile: None specified; Image: quay.io/centos/centos:stream8") 

TASK [Discover local Podman images] ********************************************
ok: [localhost] => (item=centos_7)
ok: [localhost] => (item=centos_8)
ok: [localhost] => (item=ubuntu)
ok: [localhost] => (item=instance)

TASK [Build an Ansible compatible image] ***************************************
skipping: [localhost] => (item=centos:7) 
skipping: [localhost] => (item=centos:8_update) 
skipping: [localhost] => (item=ubuntu:python) 
skipping: [localhost] => (item=quay.io/centos/centos:stream8) 

TASK [Determine the CMD directives] ********************************************
ok: [localhost] => (item="centos_7 command: None specified")
ok: [localhost] => (item="centos_8 command: None specified")
ok: [localhost] => (item="ubuntu command: None specified")
ok: [localhost] => (item="instance command: None specified")

TASK [Remove possible pre-existing containers] *********************************
changed: [localhost]

TASK [Discover local podman networks] ******************************************
skipping: [localhost] => (item=centos_7: None specified) 
skipping: [localhost] => (item=centos_8: None specified) 
skipping: [localhost] => (item=ubuntu: None specified) 
skipping: [localhost] => (item=instance: None specified) 

TASK [Create podman network dedicated to this scenario] ************************
skipping: [localhost]

TASK [Create molecule instance(s)] *********************************************
changed: [localhost] => (item=centos_7)
changed: [localhost] => (item=centos_8)
changed: [localhost] => (item=ubuntu)
changed: [localhost] => (item=instance)

TASK [Wait for instance(s) creation to complete] *******************************
FAILED - RETRYING: Wait for instance(s) creation to complete (300 retries left).
FAILED - RETRYING: Wait for instance(s) creation to complete (299 retries left).
FAILED - RETRYING: Wait for instance(s) creation to complete (298 retries left).
FAILED - RETRYING: Wait for instance(s) creation to complete (297 retries left).
FAILED - RETRYING: Wait for instance(s) creation to complete (296 retries left).
changed: [localhost] => (item=centos_7)
failed: [localhost] (item=centos_8) => {"ansible_job_id": "52972865997.554", "ansible_loop_var": "item", "attempts": 1, "changed": true, "cmd": ["/usr/bin/podman", "run", "-d", "--name", "centos_8", "--hostname=centos_8", "centos:8_update", "bash", "-c", "while true; do sleep 10000; done"], "delta": "0:00:02.137507", "end": "2022-11-14 13:48:20.768820", "finished": 1, "item": {"ansible_job_id": "52972865997.554", "ansible_loop_var": "item", "changed": true, "failed": false, "finished": 0, "item": {"image": "centos:8_update", "name": "centos_8", "pre_build_image": true}, "results_file": "/root/.ansible_async/52972865997.554", "started": 1}, "msg": "non-zero return code", "rc": 125, "start": "2022-11-14 13:48:18.631313", "stderr": "Resolved \"centos\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)\nTrying to pull quay.io/centos/centos:8_update...\nError: initializing source docker://quay.io/centos/centos:8_update: reading manifest 8_update in quay.io/centos/centos: manifest unknown: manifest unknown", "stderr_lines": ["Resolved \"centos\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)", "Trying to pull quay.io/centos/centos:8_update...", "Error: initializing source docker://quay.io/centos/centos:8_update: reading manifest 8_update in quay.io/centos/centos: manifest unknown: manifest unknown"], "stdout": "", "stdout_lines": []}
failed: [localhost] (item=ubuntu) => {"ansible_job_id": "219893954376.585", "ansible_loop_var": "item", "attempts": 1, "changed": true, "cmd": ["/usr/bin/podman", "run", "-d", "--name", "ubuntu", "--hostname=ubuntu", "ubuntu:python", "bash", "-c", "while true; do sleep 10000; done"], "delta": "0:00:02.219440", "end": "2022-11-14 13:48:21.186070", "finished": 1, "item": {"ansible_job_id": "219893954376.585", "ansible_loop_var": "item", "changed": true, "failed": false, "finished": 0, "item": {"image": "ubuntu:python", "name": "ubuntu", "pre_build_image": true}, "results_file": "/root/.ansible_async/219893954376.585", "started": 1}, "msg": "non-zero return code", "rc": 125, "start": "2022-11-14 13:48:18.966630", "stderr": "Resolved \"ubuntu\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)\nTrying to pull docker.io/library/ubuntu:python...\nError: initializing source docker://ubuntu:python: reading manifest python in docker.io/library/ubuntu: manifest unknown: manifest unknown", "stderr_lines": ["Resolved \"ubuntu\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)", "Trying to pull docker.io/library/ubuntu:python...", "Error: initializing source docker://ubuntu:python: reading manifest python in docker.io/library/ubuntu: manifest unknown: manifest unknown"], "stdout": "", "stdout_lines": []}
FAILED - RETRYING: Wait for instance(s) creation to complete (300 retries left).
changed: [localhost] => (item=instance)

PLAY RECAP *********************************************************************
localhost                  : ok=7    changed=2    unreachable=0    failed=1    skipped=5    rescued=0    ignored=0

CRITICAL Ansible return code was 2, command was: ['ansible-playbook', '--inventory', '/root/.cache/molecule/vector-role/default/inventory', '--skip-tags', 'molecule-notest,notest', '/opt/vector-role/.tox/py37-ansible210/lib/python3.7/site-packages/molecule_podman/playbooks/create.yml']
WARNING  An error occurred during the test sequence action: 'create'. Cleaning up.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy

PLAY [Destroy] *****************************************************************

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})

TASK [Wait for instance(s) deletion to complete] *******************************
FAILED - RETRYING: Wait for instance(s) deletion to complete (300 retries left).
FAILED - RETRYING: Wait for instance(s) deletion to complete (299 retries left).
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '297204121833.889', 'results_file': '/root/.ansible_async/297204121833.889', 'changed': True, 'failed': False, 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '135194697284.909', 'results_file': '/root/.ansible_async/135194697284.909', 'changed': True, 'failed': False, 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '426509798041.954', 'results_file': '/root/.ansible_async/426509798041.954', 'changed': True, 'failed': False, 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '759644026662.983', 'results_file': '/root/.ansible_async/759644026662.983', 'changed': True, 'failed': False, 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
ERROR: InvocationError for command /opt/vector-role/.tox/py37-ansible210/bin/molecule test -s default --destroy always (exited with code 1)
py37-ansible30 create: /opt/vector-role/.tox/py37-ansible30
py37-ansible30 installdeps: -rtox-requirements.txt
py37-ansible30 installed: ansible-compat==1.0.0,ansible-lint==5.1.3,arrow==1.2.3,bcrypt==4.0.1,binaryornot==0.4.4,bracex==2.3.post1,cached-property==1.5.2,Cerberus==1.3.2,certifi==2022.9.24,cffi==1.15.1,chardet==5.0.0,charset-normalizer==2.1.1,click==8.1.3,click-help-colors==0.9.1,commonmark==0.9.1,cookiecutter==2.1.1,cryptography==38.0.3,distro==1.8.0,enrich==1.2.7,idna==3.4,importlib-metadata==5.0.0,Jinja2==3.1.2,jinja2-time==0.2.0,jmespath==1.0.1,lxml==4.9.1,MarkupSafe==2.1.1,molecule==3.4.0,molecule-podman==1.0.1,packaging==21.3,paramiko==2.12.0,pathspec==0.10.2,pluggy==0.13.1,pycparser==2.21,Pygments==2.13.0,PyNaCl==1.5.0,pyparsing==3.0.9,python-dateutil==2.8.2,python-slugify==6.1.2,PyYAML==5.4.1,requests==2.28.1,rich==12.6.0,ruamel.yaml==0.17.21,ruamel.yaml.clib==0.2.7,selinux==0.2.1,six==1.16.0,subprocess-tee==0.3.5,tenacity==8.1.0,text-unidecode==1.3,typing_extensions==4.4.0,urllib3==1.26.12,wcmatch==8.4.1,yamllint==1.26.3,zipp==3.10.0
py37-ansible30 run-test-pre: PYTHONHASHSEED='4135157876'
py37-ansible30 run-test: commands[0] | molecule test -s default --destroy always
Traceback (most recent call last):
  File "/opt/vector-role/.tox/py37-ansible30/bin/molecule", line 5, in <module>
    from molecule.__main__ import main
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/molecule/__main__.py", line 22, in <module>
    from molecule.shell import main
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/molecule/shell.py", line 29, in <module>
    from molecule import command, logger
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/molecule/command/__init__.py", line 27, in <module>
    from molecule.command import base  # noqa
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/molecule/command/base.py", line 31, in <module>
    from ansiblelint.prerun import prepare_environment
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/ansiblelint/prerun.py", line 16, in <module>
    from ansiblelint.config import (
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/ansiblelint/config.py", line 167, in <module>
    if ansible_collections_path() in os.environ:
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/ansiblelint/config.py", line 117, in ansible_collections_path
    if ansible_version() >= ansible_version("2.10.0.dev0"):
  File "/opt/vector-role/.tox/py37-ansible30/lib/python3.7/site-packages/ansiblelint/config.py", line 151, in ansible_version
    stderr=subprocess.PIPE,
  File "/usr/local/lib/python3.7/subprocess.py", line 488, in run
    with Popen(*popenargs, **kwargs) as process:
  File "/usr/local/lib/python3.7/subprocess.py", line 800, in __init__
    restore_signals, start_new_session)
  File "/usr/local/lib/python3.7/subprocess.py", line 1551, in _execute_child
    raise child_exception_type(errno_num, err_msg, err_filename)
FileNotFoundError: [Errno 2] No such file or directory: 'ansible': 'ansible'
ERROR: InvocationError for command /opt/vector-role/.tox/py37-ansible30/bin/molecule test -s default --destroy always (exited with code 1)
py39-ansible210 installed: ansible==2.10.7,ansible-base==2.10.17,ansible-compat==2.2.4,ansible-lint==5.1.3,arrow==1.2.3,attrs==22.1.0,bcrypt==4.0.1,binaryornot==0.4.4,bracex==2.3.post1,Cerberus==1.3.2,certifi==2022.9.24,cffi==1.15.1,chardet==5.0.0,charset-normalizer==2.1.1,click==8.1.3,click-help-colors==0.9.1,commonmark==0.9.1,cookiecutter==2.1.1,cryptography==38.0.3,distro==1.8.0,enrich==1.2.7,idna==3.4,Jinja2==3.1.2,jinja2-time==0.2.0,jmespath==1.0.1,jsonschema==4.17.0,lxml==4.9.1,MarkupSafe==2.1.1,molecule==3.4.0,molecule-podman==1.0.1,packaging==21.3,paramiko==2.12.0,pathspec==0.10.2,pluggy==0.13.1,pycparser==2.21,Pygments==2.13.0,PyNaCl==1.5.0,pyparsing==3.0.9,pyrsistent==0.19.2,python-dateutil==2.8.2,python-slugify==6.1.2,PyYAML==5.4.1,requests==2.28.1,rich==12.6.0,ruamel.yaml==0.17.21,ruamel.yaml.clib==0.2.7,selinux==0.2.1,six==1.16.0,subprocess-tee==0.3.5,tenacity==8.1.0,text-unidecode==1.3,urllib3==1.26.12,wcmatch==8.4.1,yamllint==1.26.3
py39-ansible210 run-test-pre: PYTHONHASHSEED='4135157876'
py39-ansible210 run-test: commands[0] | molecule test -s default --destroy always
INFO     default scenario test matrix: dependency, lint, cleanup, destroy, syntax, create, prepare, converge, idempotence, side_effect, verify, cleanup, destroy
INFO     Performing prerun...
WARNING  Failed to locate command: [Errno 2] No such file or directory: 'git'
INFO     Guessed /opt/vector-role as project root directory
INFO     Using /root/.cache/ansible-lint/b984a4/roles/leolex.vectorrole symlink to current repository in order to enable Ansible to find the role using its expected full name.
INFO     Added ANSIBLE_ROLES_PATH=~/.ansible/roles:/usr/share/ansible/roles:/etc/ansible/roles:/root/.cache/ansible-lint/b984a4/roles
INFO     Running default > dependency
WARNING  Skipping, missing the requirements file.
WARNING  Skipping, missing the requirements file.
INFO     Running default > lint
INFO     Lint is disabled.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy
INFO     Sanity checks: 'podman'

PLAY [Destroy] *****************************************************************

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})

TASK [Wait for instance(s) deletion to complete] *******************************
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '749893500019.1300', 'results_file': '/root/.ansible_async/749893500019.1300', 'changed': True, 'failed': False, 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '177041816681.1318', 'results_file': '/root/.ansible_async/177041816681.1318', 'changed': True, 'failed': False, 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '339122427374.1346', 'results_file': '/root/.ansible_async/339122427374.1346', 'changed': True, 'failed': False, 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '128619790305.1373', 'results_file': '/root/.ansible_async/128619790305.1373', 'changed': True, 'failed': False, 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     Running default > syntax

playbook: /opt/vector-role/molecule/default/converge.yml
INFO     Running default > create

PLAY [Create] ******************************************************************

TASK [get podman executable path] **********************************************
ok: [localhost]

TASK [save path to executable as fact] *****************************************
ok: [localhost]

TASK [Log into a container registry] *******************************************
skipping: [localhost] => (item="centos_7 registry username: None specified") 
skipping: [localhost] => (item="centos_8 registry username: None specified") 
skipping: [localhost] => (item="ubuntu registry username: None specified") 
skipping: [localhost] => (item="instance registry username: None specified") 

TASK [Check presence of custom Dockerfiles] ************************************
ok: [localhost] => (item=Dockerfile: None specified)
ok: [localhost] => (item=Dockerfile: None specified)
ok: [localhost] => (item=Dockerfile: None specified)
ok: [localhost] => (item=Dockerfile: None specified)

TASK [Create Dockerfiles from image names] *************************************
skipping: [localhost] => (item="Dockerfile: None specified; Image: centos:7") 
skipping: [localhost] => (item="Dockerfile: None specified; Image: centos:8_update") 
skipping: [localhost] => (item="Dockerfile: None specified; Image: ubuntu:python") 
skipping: [localhost] => (item="Dockerfile: None specified; Image: quay.io/centos/centos:stream8") 

TASK [Discover local Podman images] ********************************************
ok: [localhost] => (item=centos_7)
ok: [localhost] => (item=centos_8)
ok: [localhost] => (item=ubuntu)
ok: [localhost] => (item=instance)

TASK [Build an Ansible compatible image] ***************************************
skipping: [localhost] => (item=centos:7) 
skipping: [localhost] => (item=centos:8_update) 
skipping: [localhost] => (item=ubuntu:python) 
skipping: [localhost] => (item=quay.io/centos/centos:stream8) 

TASK [Determine the CMD directives] ********************************************
ok: [localhost] => (item="centos_7 command: None specified")
ok: [localhost] => (item="centos_8 command: None specified")
ok: [localhost] => (item="ubuntu command: None specified")
ok: [localhost] => (item="instance command: None specified")

TASK [Remove possible pre-existing containers] *********************************
changed: [localhost]

TASK [Discover local podman networks] ******************************************
skipping: [localhost] => (item=centos_7: None specified) 
skipping: [localhost] => (item=centos_8: None specified) 
skipping: [localhost] => (item=ubuntu: None specified) 
skipping: [localhost] => (item=instance: None specified) 

TASK [Create podman network dedicated to this scenario] ************************
skipping: [localhost]

TASK [Create molecule instance(s)] *********************************************
changed: [localhost] => (item=centos_7)
changed: [localhost] => (item=centos_8)
changed: [localhost] => (item=ubuntu)
changed: [localhost] => (item=instance)

TASK [Wait for instance(s) creation to complete] *******************************
changed: [localhost] => (item=centos_7)
FAILED - RETRYING: Wait for instance(s) creation to complete (300 retries left).
failed: [localhost] (item=centos_8) => {"ansible_job_id": "466448594190.1708", "ansible_loop_var": "item", "attempts": 2, "changed": true, "cmd": ["/usr/bin/podman", "run", "-d", "--name", "centos_8", "--hostname=centos_8", "centos:8_update", "bash", "-c", "while true; do sleep 10000; done"], "delta": "0:00:02.189241", "end": "2022-11-14 13:50:07.587949", "finished": 1, "item": {"ansible_job_id": "466448594190.1708", "ansible_loop_var": "item", "changed": true, "failed": false, "finished": 0, "item": {"image": "centos:8_update", "name": "centos_8", "pre_build_image": true}, "results_file": "/root/.ansible_async/466448594190.1708", "started": 1}, "msg": "non-zero return code", "rc": 125, "start": "2022-11-14 13:50:05.398708", "stderr": "Resolved \"centos\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)\nTrying to pull quay.io/centos/centos:8_update...\nError: initializing source docker://quay.io/centos/centos:8_update: reading manifest 8_update in quay.io/centos/centos: manifest unknown: manifest unknown", "stderr_lines": ["Resolved \"centos\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)", "Trying to pull quay.io/centos/centos:8_update...", "Error: initializing source docker://quay.io/centos/centos:8_update: reading manifest 8_update in quay.io/centos/centos: manifest unknown: manifest unknown"], "stdout": "", "stdout_lines": []}
failed: [localhost] (item=ubuntu) => {"ansible_job_id": "86443988740.1745", "ansible_loop_var": "item", "attempts": 1, "changed": true, "cmd": ["/usr/bin/podman", "run", "-d", "--name", "ubuntu", "--hostname=ubuntu", "ubuntu:python", "bash", "-c", "while true; do sleep 10000; done"], "delta": "0:00:02.135223", "end": "2022-11-14 13:50:07.886477", "finished": 1, "item": {"ansible_job_id": "86443988740.1745", "ansible_loop_var": "item", "changed": true, "failed": false, "finished": 0, "item": {"image": "ubuntu:python", "name": "ubuntu", "pre_build_image": true}, "results_file": "/root/.ansible_async/86443988740.1745", "started": 1}, "msg": "non-zero return code", "rc": 125, "start": "2022-11-14 13:50:05.751254", "stderr": "Resolved \"ubuntu\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)\nTrying to pull docker.io/library/ubuntu:python...\nError: initializing source docker://ubuntu:python: reading manifest python in docker.io/library/ubuntu: manifest unknown: manifest unknown", "stderr_lines": ["Resolved \"ubuntu\" as an alias (/etc/containers/registries.conf.d/000-shortnames.conf)", "Trying to pull docker.io/library/ubuntu:python...", "Error: initializing source docker://ubuntu:python: reading manifest python in docker.io/library/ubuntu: manifest unknown: manifest unknown"], "stdout": "", "stdout_lines": []}
changed: [localhost] => (item=instance)

PLAY RECAP *********************************************************************
localhost                  : ok=7    changed=2    unreachable=0    failed=1    skipped=5    rescued=0    ignored=0

CRITICAL Ansible return code was 2, command was: ['ansible-playbook', '--inventory', '/root/.cache/molecule/vector-role/default/inventory', '--skip-tags', 'molecule-notest,notest', '/opt/vector-role/.tox/py39-ansible210/lib/python3.9/site-packages/molecule_podman/playbooks/create.yml']
WARNING  An error occurred during the test sequence action: 'create'. Cleaning up.
INFO     Running default > cleanup
WARNING  Skipping, cleanup playbook not configured.
INFO     Running default > destroy

PLAY [Destroy] *****************************************************************

TASK [Destroy molecule instance(s)] ********************************************
changed: [localhost] => (item={'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True})
changed: [localhost] => (item={'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True})

TASK [Wait for instance(s) deletion to complete] *******************************
FAILED - RETRYING: Wait for instance(s) deletion to complete (300 retries left).
FAILED - RETRYING: Wait for instance(s) deletion to complete (299 retries left).
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '462249291663.1898', 'results_file': '/root/.ansible_async/462249291663.1898', 'changed': True, 'failed': False, 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '827114011845.1916', 'results_file': '/root/.ansible_async/827114011845.1916', 'changed': True, 'failed': False, 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '135280756279.1955', 'results_file': '/root/.ansible_async/135280756279.1955', 'changed': True, 'failed': False, 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item'})
changed: [localhost] => (item={'started': 1, 'finished': 0, 'ansible_job_id': '298610240205.1983', 'results_file': '/root/.ansible_async/298610240205.1983', 'changed': True, 'failed': False, 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})

PLAY RECAP *********************************************************************
localhost                  : ok=2    changed=2    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0

INFO     Pruning extra files from scenario ephemeral directory
ERROR: InvocationError for command /opt/vector-role/.tox/py39-ansible210/bin/molecule test -s default --destroy always (exited with code 1)
py39-ansible30 recreate: /opt/vector-role/.tox/py39-ansible30
py39-ansible30 installdeps: -rtox-requirements.txt
py39-ansible30 installed: ansible-compat==2.2.4,ansible-lint==5.1.3,arrow==1.2.3,attrs==22.1.0,bcrypt==4.0.1,binaryornot==0.4.4,bracex==2.3.post1,Cerberus==1.3.2,certifi==2022.9.24,cffi==1.15.1,chardet==5.0.0,charset-normalizer==2.1.1,click==8.1.3,click-help-colors==0.9.1,commonmark==0.9.1,cookiecutter==2.1.1,cryptography==38.0.3,distro==1.8.0,enrich==1.2.7,idna==3.4,Jinja2==3.1.2,jinja2-time==0.2.0,jmespath==1.0.1,jsonschema==4.17.0,lxml==4.9.1,MarkupSafe==2.1.1,molecule==3.4.0,molecule-podman==1.0.1,packaging==21.3,paramiko==2.12.0,pathspec==0.10.2,pluggy==0.13.1,pycparser==2.21,Pygments==2.13.0,PyNaCl==1.5.0,pyparsing==3.0.9,pyrsistent==0.19.2,python-dateutil==2.8.2,python-slugify==6.1.2,PyYAML==5.4.1,requests==2.28.1,rich==12.6.0,ruamel.yaml==0.17.21,ruamel.yaml.clib==0.2.7,selinux==0.2.1,six==1.16.0,subprocess-tee==0.3.5,tenacity==8.1.0,text-unidecode==1.3,urllib3==1.26.12,wcmatch==8.4.1,yamllint==1.26.3
py39-ansible30 run-test-pre: PYTHONHASHSEED='4135157876'
py39-ansible30 run-test: commands[0] | molecule test -s default --destroy always
Traceback (most recent call last):
  File "/opt/vector-role/.tox/py39-ansible30/bin/molecule", line 5, in <module>
    from molecule.__main__ import main
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/molecule/__main__.py", line 22, in <module>
    from molecule.shell import main
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/molecule/shell.py", line 29, in <module>
    from molecule import command, logger
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/molecule/command/__init__.py", line 27, in <module>
    from molecule.command import base  # noqa
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/molecule/command/base.py", line 31, in <module>
    from ansiblelint.prerun import prepare_environment
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/ansiblelint/prerun.py", line 16, in <module>
    from ansiblelint.config import (
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/ansiblelint/config.py", line 167, in <module>
    if ansible_collections_path() in os.environ:
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/ansiblelint/config.py", line 117, in ansible_collections_path
    if ansible_version() >= ansible_version("2.10.0.dev0"):
  File "/opt/vector-role/.tox/py39-ansible30/lib/python3.9/site-packages/ansiblelint/config.py", line 146, in ansible_version
    proc = subprocess.run(
  File "/usr/local/lib/python3.9/subprocess.py", line 505, in run
    with Popen(*popenargs, **kwargs) as process:
  File "/usr/local/lib/python3.9/subprocess.py", line 951, in __init__
    self._execute_child(args, executable, preexec_fn, close_fds,
  File "/usr/local/lib/python3.9/subprocess.py", line 1823, in _execute_child
    raise child_exception_type(errno_num, err_msg, err_filename)
FileNotFoundError: [Errno 2] No such file or directory: 'ansible'
ERROR: InvocationError for command /opt/vector-role/.tox/py39-ansible30/bin/molecule test -s default --destroy always (exited with code 1)
___________________________________________________________ summary ___________________________________________________________
ERROR:   py37-ansible210: commands failed
ERROR:   py37-ansible30: commands failed
ERROR:   py39-ansible210: commands failed
ERROR:   py39-ansible30: commands failed

