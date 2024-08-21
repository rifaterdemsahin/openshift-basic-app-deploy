Troubleshooting Common Issues

This section includes commands to help troubleshoot common issues encountered during OpenShift deployment.

1. Delete Existing Resources

If you encounter conflicts with existing resources, delete them:

oc delete buildconfig nodejs-ex
oc delete deployment nodejs-ex
oc delete service nodejs-ex

2. Trigger a New Build

If you need to manually trigger a new build:

oc start-build nodejs-ex

3. Inspect Existing Resources

Inspect configurations to diagnose issues:

oc get buildconfig nodejs-ex -o yaml
oc get deployment nodejs-ex -o yaml
oc get service nodejs-ex -o yaml

4. Check Logs

Check logs for build or deployment issues:

oc logs build/my-new-nodejs-ex-1
oc logs deployment/my-new-nodejs-ex

5. Check Cluster Status

Check the status of the cluster:

oc status

6. Delete All Resources by Label

To delete all resources associated with a specific application:

oc delete all --selector app=my-new-nodejs-ex

7. Resize CRC Storage

If you need to resize CRC storage:

crc stop
qemu-img resize crc.qcow2 +50G  # Increase by 50 GB
crc start

After resizing the storage, expand the filesystem inside the CRC VM:

sudo growpart /dev/sda 1
sudo resize2fs /dev/sda1

### 5. **Push Changes to GitHub**

After adding the commands and documentation, push the changes:

bash
git add .
git commit -m "Add OpenShift commands and documentation"
git push origin main
```

This structure ensures that all the relevant OpenShift commands are well-documented and organized within your GitHub project.