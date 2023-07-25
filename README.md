![Image of ClamAV](https://www.clamav.net/assets/clamav-trademark.png)
# ClamAV [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE) [![Lifecycle:Stable](https://img.shields.io/badge/Lifecycle-Stable-97ca00)](https://github.com/bcgov/repomountie/blob/master/doc/lifecycle-badges.md)

ClamAV® is an open source antivirus engine for detecting trojans, viruses, malware & other malicious threats.

This is a repo setup for utilization in Red Hat Openshift.  This solution allows you to create a pod in your openshift environment to scan any file for known virus signatures, quickly and effectively.

The builds package the barebones service, and the deployment config will download latest signatures on first run.

Freshclam can be run within the container at any time to update the existing signatures.  Alternatively, you can re-deploy which will fetch the latest into the running container.

# Deployment

The templates in the [openshift/templates](./openshift/templates) will build and deploy the app.  Modify to suit your own environment.  [openshift/templates/clamav-bc.conf](./openshift/templates/clamav-bc.conf) will create your builder image (ideally in your tools project), and [openshift/templates/clamav-dc.conf](./openshift/templates/clamav-dc.conf) will create the pod deployment.  Modify the environment variables defined in both the build config and deployment config appropriately.

## Getting Help or Reporting an Issue

To report bugs/issues/feature requests, please file an [issue](../../issues)
