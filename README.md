# setup

I use asdf to manage my python versions.  See .tool-versions for the python
version I used.

First we need to set up our python venv and ansible:

```bash
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install cryptography
pip install "ansible>=2.9,<2.10"
```

# running playbook

```bash
cd playbooks
ansible-playbook example.yml -l clusters/aws/search/dev/us-east-1/cluster1
ansible-playbook example.yml -l clusters/aws/search/dev/us-east-1/cluster2
ansible-playbook example.yml -l clusters/aws/search/dev/us-west-2/cluster1
ansible-playbook example.yml -l clusters/aws/www/dev/us-east-1/cluster1
ansible-playbook example.yml -l clusters/azure/www/dev/eus2/cluster1
ansible-playbook example.yml -l clusters/gcp/www/dev/us-east4/cluster1
ansible-playbook example.yml -l clusters/gcp/www/prod/us-east4/cluster1
```
