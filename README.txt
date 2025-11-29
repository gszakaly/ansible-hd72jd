http://awx.local (admin/admin)

===================================
 SIMPLE
===================================

Create Project. A project corresponds to a Git repository, where the playbooks are.

  Resources > Projects > Add

    Name:                Test Project
    Source Control URL:  https://github.com/gszakaly/ansible-hd72jd.git

Create a template. A template defines a playbook from a project running in an execution
environment

  Resources > Templates > Add > Add job template

    Name:       Test Job Template
    Inventory:  Demo Inventory (runs the playbook in a Pod)
    Project:    Test Project
    Playbook:   hello.yaml

===================================
 FROM GROUND UP
===================================

Delete demo resources
  - Demo Job Template
  - Demo Credential
  - Demo Project
  - Demo Inventory

Create Inventory

  Inventories > Add > Add inventory > ... > Save

    Name:            Test Inventory
    Instance Groups: default (this is redundant)

Create Host localhost

  Inventories > Test Inventory > Hosts > Add

    Name: localhost
    Variables:
      ansible_connection: local

Create Project

  Resources > Projects > Add

    Name:                Test Project
    Source Control URL:  https://github.com/gszakaly/ansible-hd72jd.git

Create Template

  Resources > Templates > Add > Add job template

    Name:       Test Job Template
    Inventory:  Test Inventory
    Project:    Test Project
    Playbook:   hello.yaml
