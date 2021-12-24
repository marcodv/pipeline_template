# Pipeline Templates for all project in Noah Group

This repo is used to store and manages 
- variables versions
- stages
- jobs

across all the pipelines at GitLab group level

## Table of Content

- [Description](#description)
- [Structure](#structure)
- [Usage](#usage)

## Description

To have a better pipeline organization across all projects in Noah, this repo will be our source of truth.

This is a **continuos WIP** and it changes frequently, depends by the different cases that we'll have.

## Structure

This repo is organized in this way (WIP)

- [variables.yml](variables.yml): variables regards software versions, container registries, projects endpoints, etc etc
- [terraform_tmpl.yml](terraform_tmpl.yml): stages used to test, build, deploy artifacts or setup AWS Infrastructure via Terraform

## Usage

To use these templates, you need to include the resources that you need e.g. **terraform_tmpl.yml** or **variables.yml** in your .gitlab-ci.yml like in the example below

<pre>
include:
  - project: 'noah-energy/noah-pipelines-templates'
    file:    'variables.yml'
  - project: 'noah-energy/noah-pipelines-templates'
    file:    'terraform_tmpl.yml'
</pre>

Once you included these, you can access to the variables available at group level in this way
````
variable_name=${variable_in_variables_template}
````

If you want to include the stages available in the stages file, you use in your .gitlab-ci.yml the keyword **extends** followed by the stage name like in the example below

<pre>
run-security-scan:
  stage: run-security-scan
  extends: .module_security_scan
</pre>

**Important**: jobs, stages called in your pipeline need to be **prefixed by a dot** . 

In the previous example we pass to the directive extendes the **dotted** stage called **module_security_scan**

