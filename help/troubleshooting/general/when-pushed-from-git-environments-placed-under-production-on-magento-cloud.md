---
description: This article provides a solution for the issue where new environments are placed under the production environment on Adobe Commerce on cloud infrastructure when pushed from the git version-control system.
labels: 2.3,2.3.x,2.4,2.4.x,Magento Cloud CLI,Magento Commerce Cloud,command line,develop,git,production,staging,troubleshooting,Adobe Commerce,cloud infrastructure
title: New environments placed under production when pushed from Git
---

# New environments placed under production when pushed from Git

This article provides a solution for the issue where new environments are placed under the production environment on Adobe Commerce on cloud infrastructure when pushed from the git version-control system.

## Affected products and versions

* Adobe Commerce on cloud infrastructure, [all supported versions](https://magento.com/sites/default/files/magento-software-lifecycle-policy.pdf).

## Issue

<u>Prerequisites</u>:

Have a local git controlled clone of the project.

<u>Steps to reproduce</u>:

You need to create an integration branch from the staging branch:

1. Switch to the staging branch by running the following command in the local shell: `git checkout staging`
1. Create an integration branch from the staging branch by running the following command in the local shell: `git checkout -b <branch>`
1. Push the branch to the remote repository and set up an upstream branch by running the following command in the local shell: `git push --set-upstream origin <branch>`

<u>Expected results</u>:

The new branch is created under the staging branch.

<u>Actual results</u>:

The new branch was created under the production branch.

## Cause

This is not a bug. For setting a parent branch for another branch, the merchant should use the magento-cloud CLI.

## Solution

A parent branch can only be set after the merchant has pushed a newly created branch and activated it. Refer to [Adobe Commerce on cloud infrastructure > Bitbucket integration](https://devdocs.magento.com/cloud/integrations/bitbucket-integration.html#create-a-new-cloud-branch) in our developer documentation.

To update a parent for the existing branch on the server, please use the `magento-cloud environment:info` command in the magento-cloud CLI.

Example of usage:

 `magento-cloud environment:info parent Staging`

This will set the parent branch to "Staging" for the currently checked out branch.

## Related reading

* [Adobe Commerce on cloud infrastructure > magento-cloud CLI](https://devdocs.magento.com/cloud/reference/cli-ref-topic.html) in our developer documentation.