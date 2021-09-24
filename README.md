- [Spark! Github Usage Procedures](#spark-github-usage-procedures)
- [Philosophy](#philosophy)
- [Repository Standards](#repository-standards)
  - [Repository Names](#repository-names)
  - [License](#license)
  - [ReadMe](#readme)
  - [Branch Protection](#branch-protection)
  - [Permissions](#permissions)
- [Repository Creation](#repository-creation)
- [Permission Administration & Repository Usage](#permission-administration--repository-usage)
  - [Adding Users](#adding-users)
  - [Repository Usage](#repository-usage)
  - [Repository License](#repository-license)
    - [End of time period](#end-of-time-period)
- [End of Life](#end-of-life)

# Spark! Github Usage Procedures
This document describes how Spark! approaches and utilizes project repositories on Github. It should be used as a guide for future project repository creation and the management of existing repositories. Through following the principle in this document we hope to standardize all Github operations within the various Spark!xCDS programs.

# Philosophy

Spark! works with many projects throughout semesters, summer and projects that span semesters and years. Because of the nature of the program there is a high student turnover from semester to semester. Because of this it is important we maintain a single source of truth for project resources. For software engineering projects this means having a single github repository where the code lives, including any code from previous semesters. Data science, colabs and other project types should also store their code in an individual project repository although other resources may be stored in other locations(Google Drive etc).

# Repository Standards
## Repository Names
All names should be logical, of reasonable length and contain a prefix to identify the type of project. Current prefixes are as follows:
 - `se` Software Engineering
 - `ds` Data Science
 - `colab` Co-Lab
 - `template` Template repositories
 - `tutorial` All tutorials

## License
You should choose the most open license allowed for the specific project and client

## ReadMe
All projects should have a well written `ReadMe.md`

## Branch Protection
Projects should utilize [Github Branch Protection](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches) on `main` or `master` branches. This allows control of code by Spark! staff. Any work should be done on `dev` and merged into `master` or `main` with the review of a Spark! staff member.

## Permissions
Permissions for repositories should be given in a least privileged way possible. Unless required team members should not be added as admins or owners.

# Repository Creation
The `TEMPLATE-base-repo` should be used for all projects unless something special is required. It includes a default license(AGPLv3) and workflows to support auto-adding users, it also already includes the `dev` branch.

Templates do not support copying branch protection rules so upon creation branch protection should be enabled as follows
- Require pull request reviews before merging: 6
- Restrict users who can push to matching branches: None


# Permission Administration & Repository Usage

## Adding Users
Users can be added via the `COLLABORATORS` file. On public repos you will need to edit the file and open a PR into `dev` to be approved by the PM or Spark! staff. Private repos you can commit directly into `dev`. Since branch protection should be enabled you will not be able to commit directly to `master` or `main` but this does not affect the workflow.

## Repository Usage
Active work during a given period(semester, summer etc) should be performed in feature branches with logical names such as `new-cool-feature` not `branch 1` `branch 2` style. Optionally you can prefix your name to a branch for easier identification such as `name-super-cool-feature`. 

Work should be merged into `dev` or whatever "working master" branch the team is utilizing on a regular basis. Each merge ideally represents a discrete feature or bug that has been added or resolved.

## Repository License

Spark! aims to keep as much code open source as possible as such, we default to a "usually" open policy. Meaning we always want to request that code is made open source when possible. **You must verify this with each project partner**. Work with partners to select a license they are comfortable with utilizing.

### End of time period
 When the project has wrapped in the given time period a single PR should be made to `main` or `master` that represents all the work from that period of time. In addition, a branch with the semesters work should be created for archival purposes. For example, post Fall 2021 a branch should be created as follows: `fall-2021-work`.

 # End of Life
 When a project reaches an end of life or otherwise is completed it should be archived to be read only on Github. If possible, it should also be open sourced with as permissive of a license as possible. 
