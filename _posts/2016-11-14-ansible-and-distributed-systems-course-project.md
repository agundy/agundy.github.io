---
layout: post
title: Ansible and Distributed-Systems Course Project
tags:
  - Programming
  - Ansible
---

This semester I am taking a bunch of cool fun classes before graduation. One of those classes is Distributed Systems and Algorithms. One of our projects was a simplified implementation of a distributed file system using Raymonds algorithm. Implementation was pretty specific to the class and very constrained but something I wanted to share was my usage of Ansible. The project had to be launched in three separate regions and know information about the other hosts. I saw this as the perfect use for the dynamic inventory abilities of Ansible I've used previously.

After creating initial images and keys in Amazon Web Services in each region with the correct permissions I then created a simple playbook to launch new instances. 
```
---

- hosts: 127.0.0.1
  connection: local
  tasks:
    - name: launch Virginia instance
      ec2:
          key_name: raymonds
          instance_type: t2.micro
          image: ami-ID
          wait: yes
          vpc_subnet_id: subnet-ID
          group_id: sg-ID
          count: 1
          assign_public_ip: yes
          region: us-east-1
          ec2_url: apigateway.us-east-1.amazonaws.com 
          instance_tags:
              Name: raymonds
    - name: launch Frankfurt instance
      ec2:
          key_name: raymonds-frankfurt
          instance_type: t2.micro
          image: ami-ID
          wait: yes
          vpc_subnet_id: subnet-ID
          group_id: sg-ID
          count: 1
          assign_public_ip: yes
          region: eu-central-1
          instance_tags:
              Name: raymonds
    - name: launch Sydney instance
      ec2:
          key_name: raymonds-sydney
          instance_type: t2.micro
          image: ami-ID
          wait: yes
          vpc_subnet_id: subnet-ID
          group_id: sg-ID
          count: 1
          assign_public_ip: yes
          region: ap-southeast-2
          instance_tags:
              Name: raymonds
```
Now with the instances launched and tagged with Raymonds, I could take advantage of the AWS tags to grab all Raymonds servers and copy over the executable and configuration files. 
```
---

- hosts: tag_Name_raymonds
  user: ubuntu
  gather_facts: yes
  vars:
      node_count: 6
  tasks:
    - name: template production server json to local
      local_action: template src=servers.json.j2 dest=./server_prod.json
      run_once: true

    - template: src=servers.json.j2 dest=/home/ubuntu/servers.json owner=ubuntu mode=0644

    - copy: src=raymonds-algorithm dest=/home/ubuntu/raymonds-algorithm owner=ubuntu mode=0744

    - copy: src=tree.txt dest=/home/ubuntu/tree.txt owner=ubuntu mode=0644
```

Because our project relied on shell access and viewing the logs as they happened I didn't need to set up any services or workers. Two quick playbooks and I could than easily copy over and update the hosts on demand. When it came time to demo the project a new `tree.txt` file was given and one line updated the file to all the hosts.

The hardest part of this configuration was created the initial security groups, AMI's and keys and having Ansible connect to them. Once that was set up it was easy to reason about and update. I had a great experience using Ansible on a small scale (3 node) automation setup and would definitely consider using it in projects again.

