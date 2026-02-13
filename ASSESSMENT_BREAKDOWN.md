# Assessment Breakdown

Write code to appropriately automate common actions such as software testing and deployment.

Using a CI/CD platform, write automation workflow files for that platform that:

- Contain instructions to install or otherwise initialise an existing application in a CI/CD environment
- Execute compilation, testing, OR configuration actions when run by the platform.
- Push new deployments to an appropriate cloud platform.
- Configure any connections between the deployment and required services.

The README OR other documentation must explain:

- WHAT CI/CD tools and systems were chosen (e.g. GitHub Actions)
- WHAT those specific tools or systems do AND will be used for
- WHY those specific tools or systems were chosen over alternatives
  - _Ed content has good content on this_

The workflow files must:

- Be syntactically correct and execute successfully
- Use DRY programming principles
- Successfully deploy an application
- Install application dependencies required by package dependency file(s).
- Run an automated test suite with multiple different tests. All tests must pass.
- Configure required services (such as file storage or databases) with appropriate credentials and environment settings.
  - _Don't need to know credentials within submission, but need to see that you have things like database URL or connection string in your repository secrets, used or referred by your workflow as a secret/environment variable_
- Deploy to an appropriate cloud hosting service (such as Google Cloud Run in Google Cloud Platform or AWS EC2 in Amazon Web Services).
  - _React on EC2 is not appropriate, inefficient use of resources_

---

## Rubric Breakdown

### 1. DEVELOPS semantically and syntactically valid & complete automation workflow files. 10%

Implements at least ONE automation workflow file(s) OR help file(s) which are COMPLETELY semantically & syntactically valid.

- ✅ Currently THREE workflows implemented

### 2. CREATES appropriate files or commands to automate a testing process. 15%

Uses at least ONE automation workflow file to automate a testing process at a DETAILED level, such as building a custom log file out of the testing results. Plus uses the automation workflow to store logs in a persistent location.

- ✅ At least ONE workflow file
- ✅ Custom log file with test results
- ✅ Automation workflow stores logs in persistent location
  - _Can be saving them as artifacts or as comments on a pull request, just having them persist in some way_

### 3. CREATES appropriate files or commands to automate a deployment process. 15%

Uses at least ONE automation workflow to automate deployment at a BASIC level, such as deploying to a cloud hosting service. Plus uses at least ONE environment variable appropriately. Plus uses environment-specific settings & connections for databases & other services. Plus uses automation workflow to preserve deployment revisions in a cloud hosting service.

- ✅ ONE deployment workflow implemented
- ✅ MULTIPLE environment variables used appropriately
- ✅ Uses environment-specific settings & connections for databases & other services
- ✅ Workflow preserves deployment revisions in cloud hosting service

### 4. CREATES appropriate triggers for an automation workflow. 10%

Uses at least TWO CI/CD workflow triggers OR events at a complex level to initiate an automated workflow, including conditions, schedules, or dependent workflows.

- ✅ `ci-test.yaml` triggers on pull_request
- ✅ `build-and-push.yaml` triggers on version bump
- ✅ `deploy.yaml` triggers on successful completion of `build-and-push.yaml`

### 5. DEVELOPS optimised automation workflow scripts to a professional level. 10%

Uses variables & other reusable code to optimise an automated workflow. Plus uses env variables where appropriate. Plus uses secrets or encrypted keys in an optimal, secure way. Plus creates AT LEAST ONE of the following: writing a custom action/plugin to use within a workflow, export workflow files as downloadable items, export workflow data to reuse in additional workflows.

- ❓ Uses variables & other reusable code to optimise an automated workflow
- ❓ Uses env variables where appropriate.
- ❓ Uses secrets or encrypted keys in an optimal, secure way
- ✅ Exports workflow data to reuse in other workflows (`build-and-push.yaml` uploads tag artifact used by `deploy.yaml`)

### 6. EXPLAINS the purpose & functionalities of an automation workflow. 20%

EXTENSIVE explanation of ALL of the purpose & functionalities of an automation workflow, with diagrams and examples.
_Flowcharts can be from this step, we move to this one. Examples can be with this file we get this result. with this particular PR or branch name we get this result._

- ❌ Explains PURPOSE of all automation workflows
- ✅ Explains FUNCTIONALITY of all automation workflows
- ✅ Uses DIAGRAMS in explanations
- ❓ Uses EXAMPLES in explanations

### 7. EXPLAINS the relations & dependencies of services & technologies involved in an application managed by a CI/CD platform. 20%

EXTENSIVE explanation of ALL of the services & technologies used by an application managed by a CI/CD platform. Plus comparison to alternative software. Plus diagrams and examples included in explanation.
_If you're deploying an express server and it depends on a MongoDB database, you would point out it depends on that database being deployed somewhere, and talk about how your workflow connects those two services together. Like is there a secret you have to pass in to your server? How do you ensure your MongoDB database is available?_
_For a React app, making sure you know the API URL that the app needs to use_

- ❓ Extensive explanation of all services and technologies used by application managed by CI/CD platform
- ❓ Comparison to alternative software
  - _How it might impact your CI/CD workflow_
- ❓ Diagrams and examples included in explanation

---

## Priority Questions

1. If my deployment service isn't free and I'm out of free credits, is it fine to have proof of successful deployment without having it live?
2. Is the deployment to ECS appropriate for the front end?

## Rubric

<!-- prettier-ignore -->
| **Task Descriptor** | **(HD) High Distinction (85-100%)** |
| :---: | :---: |
| **DEVELOPS semantically and syntactically valid & complete automation workflow files. 10% SLO 5** | Implements at least one automation workflow files or help files which are COMPLETELY semantically & syntactically valid. |
| **CREATES appropriate files or commands to automate a testing process 15% SLO 3, SLO 4, SLO 5** | Uses at least ONE automation workflow file to automate a testing process at a DETAILED level, such as building a custom log file out of the testing results. Plus uses the automation workflow to store logs in a persistent location. |
| **CREATES appropriate files or commands to automate a deployment process 15% SLO 6** | Uses at least ONE automation workflow to automate deployment at a BASIC level, such as deploying to a cloud hosting service. Plus uses at least ONE environment variable appropriately. Plus uses environment-specific settings & connections for databases & other services. Plus uses automation workflow to preserve deployment revisions in a cloud hosting service. |
| **CREATES appropriate triggers for an automation workflow 10% SLO 5** | Uses at least TWO continuous integration/continuous delivery (CI/CD) workflow triggers or events at a complex level to initiate an automated workflow, including conditions, schedules, or dependent workflows. |
| **DEVELOPS optimised automation workflow scripts to a professional level 10% SLO 3, SLO 5** | Uses variables & other reusable code to optimise an automated workflow. Plus uses env variables where appropriate. Plus uses secrets or encrypted keys in an optimal, secure way. Plus creates AT LEAST ONE of the following: writing a custom action/plugin to use within a workflow, export workflow files as downloadable items, export workflow data to reuse in additional workflows. |
| **EXPLAINS the purpose & functionalities of an automation workflow 20% SLO 3, SLO 4** | EXTENSIVE explanation of ALL of the purpose & functionalities of an automation workflow, with diagrams and examples. |
| **EXPLAINS the relations & dependencies of services & technologies involved in an application managed by a continuous integration/continuous delivery (CI/CD) platform 20% SLO 3, SLO 4, SLO 5, SLO 6** | EXTENSIVE explanation of ALL of the services & technologies used by an application managed by a continuous integration/continuous delivery (CI/CD), comparison to alternative software, and with the explanation including diagrams and examples. |

<!-- prettier-ignore -->
<!-- | **Task Descriptor** | **(HD) High Distinction (85-100%)** | **(D) Distinction (75-84%)** | **(C) Credit (65-74%)** | **(P) Pass (50-64%)** | **(F) Fail (0-49%)** |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **DEVELOPS semantically and syntactically valid & complete automation workflow files. 10% SLO 5** | Implements at least one automation workflow files or help files which are COMPLETELY semantically & syntactically valid. | Implements at least one automation workflow files or help files which are ALMOST COMPLETELY semantically & syntactically valid. | Implements at least one automation workflow files or help files which are MOSTLY semantically & syntactically valid. | Implements at least one automation workflow files or help files which are SOMEWHAT semantically & syntactically valid. | The relevant automation workflow files either do not exist or are almost entirely semantically & syntactically invalid. |
| **CREATES appropriate files or commands to automate a testing process 15% SLO 3, SLO 4, SLO 5** | Meets D criteria, plus uses the automation workflow to store logs in a persistent location. | Uses at least ONE automation workflow file to automate a testing process at a DETAILED level, such as building a custom log file out of the testing results. | Uses at least ONE automation workflow file to automate a testing process at a SOMEWHAT-BASIC level, such as running a test suite with formatted output. | Uses at least ONE automation workflow file to automate a testing process at a BASIC level, such as running a test suite with default output. | The automation workflow file is either syntactically invalid, or does not facilitate automated testing, or no tests are carried out. |
| **CREATES appropriate files or commands to automate a deployment process 15% SLO 6** | Meets D criteria, plus uses the automation workflow to preserve deployment revisions in a cloud hosting service. | Meets C criteria, plus uses environment-specific settings & connections for databases & other services. | Meets P criteria, plus uses at least one environment variable appropriately. | Uses at least ONE automation workflow file to automate a deployment process at a BASIC level, such as deploying an app to a cloud hosting service. | The automation workflow file is either syntactically invalid, or does not facilitate automated deployment, or no deployment is carried out. |
| **CREATES appropriate triggers for an automation workflow 10% SLO 5** | Uses at least TWO continuous integration/continuous delivery (CI/CD) workflow triggers or events at a complex level to initiate an automated workflow, including conditions, schedules, or dependent workflows. | Uses at least ONE continuous integration/continuous delivery (CI/CD) workflow triggers or events at a complex level to initiate an automated workflow, including conditions, schedules, or dependent workflows. | Uses at least TWO continuous integration/continuous delivery (CI/CD) workflow triggers or events at a basic level to initiate an automated workflow. | Uses at least ONE continuous integration/continuous delivery (CI/CD) workflow triggers or events at a basic level to initiate an automated workflow. | The automation workflow file is either syntactically invalid, or does not use any appropriate triggers. |
| **DEVELOPS optimised automation workflow scripts to a professional level 10% SLO 3, SLO 5** | Meets D criteria, plus creates functionality to cover AT LEAST ONE of the following: writing a custom action/plugin to use within a workflow, export workflow files as downloadable items, export workflow data to reuse in additional workflows. | Meets C criteria, plus uses secrets or encrypted keys in an optimal, secure way. | Meets P criteria, plus uses environment variables where appropriate. | Uses variables & other reusable code to optimise an automated workflow. | The automation workflow file makes no use of required optimization techniques. |
| **EXPLAINS the purpose & functionalities of an automation workflow 20% SLO 3, SLO 4** | EXTENSIVE explanation of ALL of the purpose & functionalities of an automation workflow, with diagrams and examples. | MODERATELY-DETAILED explanation of ALL of the purposes & functionalities of an automation workflow, with diagrams or examples. | EXTENSIVE explanation of SOME of the purpose & functionalities of an automation workflow, with diagrams and examples. | MODERATELY-DETAILED explanation of SOME of the purpose & functionalities of an automation workflow, with diagrams or examples. | Explanation provided is either completely incorrect, not containing relevant details, or not provided at all. |
| **EXPLAINS the relations & dependencies of services & technologies involved in an application managed by a continuous integration/continuous delivery (CI/CD) platform 20% SLO 3, SLO 4, SLO 5, SLO 6** | EXTENSIVE explanation of ALL of the services & technologies used by an application managed by a continuous integration/continuous delivery (CI/CD), comparison to alternative software, and with the explanation including diagrams and examples. | MODERATELY-DETAILED explanation of ALL of the services & technologies used by an application managed by a continuous integration/continuous delivery (CI/CD), comparison to alternative software, and with the explanation including diagrams and examples. | EXTENSIVE explanation of SOME of the services & technologies used by an application managed by a continuous integration/continuous delivery (CI/CD), with diagrams and examples. | MODERATELY-DETAILED explanation of SOME of the services & technologies used by an application managed by a continuous integration/continuous delivery (CI/CD), with diagrams or examples. | Explanation provided is either completely incorrect, not containing relevant details, or not provided at all. | -->

<!-- prettier-ignore -->
