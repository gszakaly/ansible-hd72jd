http://awx.local (admin/admin)

Create Project. A project corresponds to a Git repository, where the playbooks are.

  Resources > Projects > Add

    Name:                Test
    Source Control URL:  https://github.com/gszakaly/ansible-hd72jd.git

Create a template. A template defines a playbook from a project running in an execution
environment

  Resources > Templates > Add > Add job template

    Name:                   Test
    Inventory:              Demo Inventory (not sure how it works, but this runs the playbook in a Pod)
    Project:                Test
    Playbook:               hello.yaml

