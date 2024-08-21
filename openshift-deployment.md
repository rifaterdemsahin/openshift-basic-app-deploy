Document the commands for deploying applications on OpenShift:

# Deploying Applications on OpenShift

This guide provides commands for deploying a sample Node.js application, a Django application, and a Golang application on OpenShift.

### 1. **Log in to the OpenShift Cluster**

Use the `oc` command-line tool to log in:

bash
oc login

### 2. **Create a New Project**

Create a new project in OpenShift:

bash
oc new-project myapp-project

### 3. **Deploy a Sample Node.js Application**

Deploy a sample Node.js application using OpenShift’s source-to-image (S2I) feature:

bash
oc new-app nodejs~https://github.com/sclorg/nodejs-ex -n myapp-project

### 4. **Deploy a Django Application**

Deploy a Django application:

bash
oc new-app python:3.8~https://github.com/sclorg/django-ex -n myapp-project

### 5. **Deploy a Golang Application**

Deploy a Golang application:

bash
oc new-app golang~https://github.com/sclorg/golang-ex -n myapp-project

### 6. **Monitor the Deployment**

Monitor the deployment process:

bash
oc status

Check build logs for a specific application:

bash
oc logs -f bc/nodejs-ex

### 7. **Expose the Service**

Create an external route to expose the application:

bash
oc expose svc/nodejs-ex

Verify the route and get the application URL:

bash
oc get routes

### 8. **Scale the Application**

Scale the number of pods:

bash
oc scale --replicas=3 dc/nodejs-ex

### 9. **Clean Up Resources**

Delete the project and all associated resources:

bash
oc delete project myapp-project

### 4. **troubleshooting.md**

Include commands useful for troubleshooting issues: