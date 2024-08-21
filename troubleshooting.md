Here’s a sample `troubleshooting.md` file that you can use in your GitHub project. This file includes common issues that users might encounter when deploying applications on OpenShift using CodeReady Containers (CRC) and how to resolve them.

### Sample `troubleshooting.md`

```markdown
# Troubleshooting Guide

This guide addresses common issues encountered when deploying applications on OpenShift using CodeReady Containers (CRC). If you run into problems, the solutions provided here should help you resolve them.

## Table of Contents
- [Deleting Existing Resources](#deleting-existing-resources)
- [Failed Builds](#failed-builds)
- [Service Not Found](#service-not-found)
- [Low Ephemeral Storage](#low-ephemeral-storage)
- [Increasing CRC Disk Size](#increasing-crc-disk-size)
- [Access Issues in CRC](#access-issues-in-crc)
- [Stuck CRC Setup](#stuck-crc-setup)
- [General Cluster Issues](#general-cluster-issues)

## Deleting Existing Resources

If you encounter conflicts with existing resources (e.g., when re-deploying an application), you can delete them using the following commands:

```bash
oc delete buildconfig nodejs-ex
oc delete deployment nodejs-ex
oc delete service nodejs-ex
```

You can also delete all resources associated with an application:

```bash
oc delete all --selector app=my-new-nodejs-ex
```

## Failed Builds

If a build fails, the following commands can help you diagnose and resolve the issue:

1. **Check Build Logs**:
    ```bash
    oc logs build/my-new-nodejs-ex-1
    ```

2. **Inspect Build Configuration**:
    ```bash
    oc get buildconfig my-new-nodejs-ex -o yaml
    ```

3. **Manually Trigger a New Build**:
    ```bash
    oc start-build nodejs-ex
    ```

## Service Not Found

If you receive an error indicating that a service was not found:

1. **Verify Application Deployment**:
    ```bash
    oc get all -n myapp-project
    ```

2. **Create and Expose the Service Manually**:
    ```bash
    oc expose deployment/golang-ex --port=8080 -n myapp-project
    oc expose svc/golang-ex -n myapp-project
    ```

## Low Ephemeral Storage

If you encounter an error related to low ephemeral storage:

1. **Check Disk Usage**:
    ```bash
    df -h
    ```

2. **Clean Up Unnecessary Files**: Use tools like `du` to identify large files or directories.

3. **Evict or Reschedule Pods**: Consider rescheduling non-essential pods to other nodes.

## Increasing CRC Disk Size

If you need to increase the available storage in CRC:

1. **Stop CRC**:
    ```bash
    crc stop
    ```

2. **Resize the CRC Disk**:
    - On Linux/macOS:
        ```bash
        qemu-img resize crc.qcow2 +50G
        ```
    - On Windows:
        ```powershell
        Resize-VHD -Path "C:\Users\<YourUsername>\.crc\machines\crc\crc.vhdx" -SizeBytes 100GB
        ```

3. **Start CRC Again**:
    ```bash
    crc start
    ```

4. **Expand Filesystem Inside CRC**:
    ```bash
    sudo growpart /dev/sda 1
    sudo resize2fs /dev/sda1
    ```

## Access Issues in CRC

If you have trouble accessing CRC (e.g., login failures):

1. **Use the Default Login**:
    - Username: `core`
    - Password: (usually empty, just press Enter)

2. **Resetting Passwords**: If you've changed the default setup, consult the CRC documentation to reset credentials.

## Stuck CRC Setup

If the CRC setup is stuck, particularly during the "Operator network is progressing" stage:

1. **Wait Longer**: The setup process may take additional time.

2. **Check System Resources**: Ensure your system meets the minimum requirements for CRC.

3. **Review CRC Logs**:
    ```bash
    crc log --follow
    ```

4. **Re-run CRC Setup**:
    ```bash
    crc stop
    crc delete
    crc start
    ```

## General Cluster Issues

If the cluster is up but has issues:

1. **Check Cluster Status**:
    ```bash
    oc status
    ```

2. **Inspect Cluster Operators**:
    ```bash
    oc get co
    oc describe <operator-name>
    ```

If these solutions don't resolve your issue, consider consulting the OpenShift documentation or seeking help from the community forums.
```

### Steps to Add and Push the `troubleshooting.md`

1. **Create the `troubleshooting.md` File**
   - In your project directory, create the file:
     ```bash
     touch troubleshooting.md
     ```
   - Open `troubleshooting.md` in a text editor and paste the content provided above.

2. **Add the File to Git**
   ```bash
   git add troubleshooting.md
   ```

3. **Commit the Changes**
   ```bash
   git commit -m "Add troubleshooting guide"
   ```

4. **Push to GitHub**
   ```bash
   git push origin main
   ```

This `troubleshooting.md` file will serve as a useful reference for resolving common issues users might encounter when working with OpenShift on CRC.
