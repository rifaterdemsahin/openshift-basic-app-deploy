Here’s the markdown document with the `resize` parameter included in the setup instructions for CodeReady Containers (CRC):

---

# Setting Up CodeReady Containers (CRC)

Follow these steps to set up CodeReady Containers (CRC) on your local machine for deploying and managing applications on OpenShift.

## 1. Install CRC

### Download CRC
1. **Download the latest version of CRC** from the [official Red Hat CodeReady Containers website](https://developers.redhat.com/products/codeready-containers/overview).

### Install CRC
2. **Extract the downloaded file** and add the CRC binary to your system's `PATH` so it can be accessed from any command line interface.

## 2. Set Up CRC

Before starting CRC, you can specify the amount of disk space allocated to the CRC virtual machine using the `disk-size` parameter. This can be useful if you anticipate needing more storage space for your OpenShift workloads.

### Set the Disk Size (Optional)

To allocate more storage, configure the disk size (e.g., 100 GB):

```bash
crc config set disk-size 100
```

### Run the Setup Command

After configuring (or if you choose to use the default settings), run the following command to set up CRC:

```bash
crc setup
```

## 3. Start CRC

Start the OpenShift cluster with the following command:

```bash
crc start
```

During the start process, you will be prompted to enter your pull secret, which you can obtain from the same Red Hat OpenShift page where you downloaded CRC.

## 4. Access OpenShift

Once CRC is running, you can access the OpenShift web console by navigating to the URL provided during the CRC start process (usually `https://console-openshift-console.apps-crc.testing`).

Log in using the credentials provided by CRC, typically with the username `kubeadmin` and the password displayed after the CRC start command completes.

---

This guide now includes the optional step for resizing the CRC disk size before setup, which is crucial for users who require more storage for their OpenShift environment.
