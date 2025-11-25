http://awx.local (admin/admin)

Create Project. A project corresponds to a Git repository, where the playbooks are.

  Resources > Projects > Add

    Name:                Test
    Source Control URL:  https://github.com/gszakaly/ansible-hd72jd.git

Create execution environment. An execution environment defines the image of the Pod
that is running the playbook.

  Administration > Execution Environments > Add

    Name:   Alpine
    Image:  alpine:3.22.2

Create a template. A template defines a playbook from a project running in an execution
environment

  Resources > Templates > Add > Add job template

    Name:                   Test
    Inventory:              Demo Inventory (not sure how it works, but this runs the playbook in a Pod)
    Project:                Test
    Execution Environment:  Alpine
    Playbook:               hello.yaml

