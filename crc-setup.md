# Setting Up CodeReady Containers (CRC)

Follow these steps to set up CodeReady Containers (CRC) on your local machine.

### Install CRC
1. **Download CRC**:
   - Download the latest version of CRC from the [official Red Hat CodeReady Containers website](https://developers.redhat.com/products/codeready-containers/overview).

2. **Install CRC**:
   - Extract the downloaded file and add the CRC binary to your PATH.

3. **Set Up CRC**:
   - Run the following command to set up CRC:
     ```bash
     crc setup
     ```

4. **Start CRC**:
   - Start the OpenShift cluster:
     ```bash
     crc start
     ```

5. **Access OpenShift**:
   - Access the OpenShift web console using the URL provided during the CRC start process (usually `https://console-openshift-console.apps-crc.testing`).
   - Log in using the credentials provided by CRC.