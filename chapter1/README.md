# Installation procedure for Red Hat Ansible Engine 2

1. Register your system to Red Hat Subscription Manager.

    ```
    [root@host ~]# subscription-manager register
    ```
2. Set a role for your system.

    ```
    [root@host ~]# subscription-manager role --set="Red Hat Enterprise Linux Server"
    ```
3. Attach your Red Hat Ansible Engine subscription. This command helps you find your Red Hat Ansible Engine subscription:

    ```
    [root@host ~]# subscription-manager list --available
    ```

4. Use the pool ID of the subscription to attach the pool to the system.

    ```
    [root@host ~]# subscription-manager attach --pool=<engine-subscription-pool>
    ```

5. Enable the Red Hat Ansible Engine repository.

    ```
    [root@host ~]# subscription-manager repos --enable ansible-2-for-rhel-8-x86_64-rpms
    ```

6. Install Red Hat Ansible Engine.

    ```
    [root@host ~]# yum install ansible
    ```

7. Verify that Ansible is installed on the system. Execute the ansible command with the --version option.

    ```
    [root@host ~]# ansible --version
    ```

If you are using the version with limited support provided with your Red Hat Enterprise Linux
subscription, use the following procedure:

1. Enable the Red Hat Ansible Engine repository.

    ```
    [root@host ~]# subscription-manager refresh
    [root@host ~]# subscription-manager repos --enable ansible-2-for-rhel-8-x86_64-rpms
    ```

2. Install Red Hat Ansible Engine.

    ```
    [root@host ~]# yum install ansible
    ```

3. Verify the ansible_python_version on the localhost by using the setup module.

    ```
    [root@host ~]# ansible -m setup localhost | grep ansible_python_version
    ```
