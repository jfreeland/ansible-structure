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

This is how you can run the playbooks in the tree-like structure that I prefer.

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

This is how you can run playbooks my example playbook of what I typically see as
ansible examples.  I did not get this working and had to move on to other things
for the time being.  Problems with hostvars not picking up CLUSTER_REGION.

```bash
cd common-example
ansible-playbook example.yml -l cluster_aws_search_dev_us-east-1_cluster1
ansible-playbook example.yml -l cluster_aws_search_dev_us-east-1_cluster2
```
