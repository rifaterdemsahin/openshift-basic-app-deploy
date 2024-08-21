Here’s a more refined markdown document that outlines the commands for deploying applications on OpenShift:

---

# Deploying Applications on OpenShift

This guide provides step-by-step instructions for deploying sample Node.js, Django, and Golang applications on OpenShift using the `oc` command-line tool.

## 1. Log in to the OpenShift Cluster

First, log in to your OpenShift cluster using the `oc` command:

```bash
oc login
```

## 2. Create a New Project

Create a new project to host your applications:

```bash
oc new-project myapp-project
```

Replace `myapp-project` with the desired name for your project.

## 3. Deploy a Sample Node.js Application

Deploy a Node.js application using OpenShift’s Source-to-Image (S2I) feature:

```bash
oc new-app nodejs~https://github.com/sclorg/nodejs-ex -n myapp-project
```

## 4. Deploy a Django Application

Deploy a Django application with the following command:

```bash
oc new-app python:3.8~https://github.com/sclorg/django-ex -n myapp-project
```

## 5. Deploy a Golang Application

Deploy a Golang application:

```bash
oc new-app golang~https://github.com/sclorg/golang-ex -n myapp-project
```

## 6. Monitor the Deployment

To monitor the status of your deployments, use the following commands:

Check the overall status:

```bash
oc status
```

To view the build logs for a specific application, such as the Node.js application:

```bash
oc logs -f bc/nodejs-ex
```

## 7. Expose the Service

Make your application accessible externally by creating a route:

```bash
oc expose svc/nodejs-ex
```

To verify the route and obtain the URL for accessing your application:

```bash
oc get routes
```

## 8. Scale the Application

If you need to scale the number of running pods for your application, use:

```bash
oc scale --replicas=3 dc/nodejs-ex
```

This example scales the Node.js application to 3 replicas. Adjust the number as needed.

## 9. Clean Up Resources

When you’re done and want to remove all resources associated with your project, delete the project with:

```bash
oc delete project myapp-project
```

This will remove the project and all its resources from your OpenShift cluster.

---

This guide is organized to provide a clear and concise set of commands for deploying and managing applications on OpenShift. Each section is targeted at a specific task, ensuring that the process is straightforward for users.
