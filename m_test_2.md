
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
[33mchanged: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '95787338884.8285', 'results_file': '/home/leolex/.ansible_async/95787338884.8285', 'changed': True, 'item': {'image': 'centos:7', 'name': 'centos_7', 'pre_build_image': True}, 'ansible_loop_var': 'item'})[0m
[1;30mFAILED - RETRYING: [localhost]: Wait for instance(s) creation to complete (300 retries left).[0m
[31mfailed: [localhost] (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '309700712947.8313', 'results_file': '/home/leolex/.ansible_async/309700712947.8313', 'changed': True, 'item': {'image': 'centos:8_update', 'name': 'centos_8', 'pre_build_image': True}, 'ansible_loop_var': 'item'}) => {"ansible_job_id": "309700712947.8313", "ansible_loop_var": "item", "attempts": 2, "changed": false, "finished": 1, "item": {"ansible_job_id": "309700712947.8313", "ansible_loop_var": "item", "changed": true, "failed": 0, "finished": 0, "item": {"image": "centos:8_update", "name": "centos_8", "pre_build_image": true}, "results_file": "/home/leolex/.ansible_async/309700712947.8313", "started": 1}, "msg": "Error pulling image centos:8_update - 404 Client Error for http+docker://localhost/v1.41/images/create?tag=8_update&fromImage=centos: Not Found (\"manifest for centos:8_update not found: manifest unknown: manifest unknown\")", "results_file": "/home/leolex/.ansible_async/309700712947.8313", "started": 1, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}[0m
[31mfailed: [localhost] (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '723048935072.8340', 'results_file': '/home/leolex/.ansible_async/723048935072.8340', 'changed': True, 'item': {'image': 'ubuntu:python', 'name': 'ubuntu', 'pre_build_image': True}, 'ansible_loop_var': 'item'}) => {"ansible_job_id": "723048935072.8340", "ansible_loop_var": "item", "attempts": 1, "changed": false, "finished": 1, "item": {"ansible_job_id": "723048935072.8340", "ansible_loop_var": "item", "changed": true, "failed": 0, "finished": 0, "item": {"image": "ubuntu:python", "name": "ubuntu", "pre_build_image": true}, "results_file": "/home/leolex/.ansible_async/723048935072.8340", "started": 1}, "msg": "Error pulling image ubuntu:python - 404 Client Error for http+docker://localhost/v1.41/images/create?tag=python&fromImage=ubuntu: Not Found (\"manifest for ubuntu:python not found: manifest unknown: manifest unknown\")", "results_file": "/home/leolex/.ansible_async/723048935072.8340", "started": 1, "stderr": "", "stderr_lines": [], "stdout": "", "stdout_lines": []}[0m
[33mchanged: [localhost] => (item={'failed': 0, 'started': 1, 'finished': 0, 'ansible_job_id': '995380219166.8447', 'results_file': '/home/leolex/.ansible_async/995380219166.8447', 'changed': True, 'item': {'image': 'quay.io/centos/centos:stream8', 'name': 'instance', 'pre_build_image': True}, 'ansible_loop_var': 'item'})[0m

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

