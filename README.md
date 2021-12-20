# Pipeline Templates for all project in Noah Group

This repo is used to store and manages 
- variables versions
- stages
- jobs

across all the pipelines at GitLab group level

## Description

To have a better pipeline organization across all projects in Noah, this repo will be our source of truth.

This is a **continuos WIP** and it changes frequently, depends by the different cases that we'll have.

## Structure

This repo is organized in this way (WIP)

- [variables.yml](https://gitlab.com/noah-energy/noah-pipelines-templates/-/blob/develop/variables.yml): variables regards software versions, container registries, projects endpoints, etc etc
- stages.yml: stages used to test, build, deploy artifacts or setup AWS Infrastructure via Terraform