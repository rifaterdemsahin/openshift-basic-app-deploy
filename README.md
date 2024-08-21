# OpenShift Basic App Deployment

This repository contains a comprehensive guide for deploying basic applications on OpenShift using CodeReady Containers (CRC). It includes instructions for setting up the environment, deploying sample applications, and troubleshooting common issues.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [CRC Setup](#crc-setup)
- [Deploying Applications](#deploying-applications)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Introduction
Deploying applications on OpenShift can be complex, especially for beginners. This project simplifies the process by providing step-by-step instructions for setting up a local OpenShift environment and deploying sample applications using the OpenShift CLI (`oc`).

## Prerequisites
Before you begin, ensure you have the following:
- Access to an OpenShift cluster (via CRC or OpenShift Online)
- Installed OpenShift CLI (`oc`)
- A machine that meets the minimum system requirements for CRC

## CRC Setup
To get started with CRC, follow our detailed [CRC Setup Guide](crc-setup.md). This guide covers everything from installation to accessing the OpenShift web console.

## Deploying Applications
We provide several examples of deploying different types of applications on OpenShift:
- [Deploy a Node.js Application](openshift-deployment.md#deploy-a-sample-nodejs-application)
- [Deploy a Django Application](openshift-deployment.md#deploy-a-django-application)
- [Deploy a Golang Application](openshift-deployment.md#deploy-a-golang-application)

These guides include all necessary `oc` commands to create projects, deploy applications, and expose them to external access.

## Troubleshooting
Encountering issues? Check out our [Troubleshooting Guide](troubleshooting.md) for solutions to common problems, such as failed builds, storage issues, and more.

## Contributing
We welcome contributions to improve these guides and examples. Please fork the repository, make your changes, and submit a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.