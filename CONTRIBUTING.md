# Contributing

The following is a set of guidelines for contributing to MBot Robotics Ecosystem and its repositories, which are hosted in the [mbot-project](https://github.com/mbot-project) Organization on GitHub.

## Navigation
- [Ecosystem Structure](#ecosystem-structure)
- [Development Protocol](#development-protocol)
  - [Branch Management Guidelines](#branch-management-guidelines)
  - [Pull Request](#pull-request-pr)
  - [README](#readme)
  - [Versioning](#versioning)
  - [Releasing](#releasing)
  - [Guidelines for Migrating to GitLab](#guidelines-for-migrating-to-gitlab)


## Ecosystem Structure

- Public:
  - mbot_sys_utils
  - mbot_lcm_base
  - mbot_firmware
  - rplidar_lcm_driver
  - mbot_web_app
  - mbot_gui
  - mbot_bridge
  - mbot_autonomy_template
  - mbot_apriltag
  - mbot_hardware
- Private:
  - mbot_autonomy


[This doc](./Codebase_Guide.md) explains each repository in detail.

## Development Protocol


### Branch Management Guidelines

`main`
- Purpose: Hosts the stable release version of the project.
- Policy: Direct merges to `main` are strictly prohibited. Any modifications for `main` must undergo a review process by Dr. Peter Gaskell or the current maintainer.

`dev`
- Purpose: Serves as the integration branch for features, bug fixes, and other changes before they are released.
- Merge Policy: To merge changes into `dev`, create a pull request and designate Dr. Peter Gaskell or the current maintainer for review.

`feature/`
- Purpose: Supports the development of new features, e.g., `feature/new-controller`.
- Workflow: Branch off from the latest `dev` branch. Once the feature is complete and has reviewed, merge it back into `dev`. After the merge, delete the feature branch to maintain a clean repository.

`bugfix/`
- Purpose: Addresses bug fixes, e.g., `bugfix/oled-display-ip-cutoff`.
- Workflow: Start from `dev` and merge back after the fix is verified and reviewed. Delete the bugfix branch post-merge to avoid clutter.

`release/`
- Purpose: Prepares for a new production release, e.g., `release/1.0.0`.
- Workflow: Branch off from `dev` when the codebase reaches a stable point. After final testing and approval, merge into `main`, tag with the version number, and then delete the release branch to keep the branch list concise.

**Naming Rules**
1. Always use lowercase to avoid case-sensitive issues.
2. Use hyphens for separation.
3. Ensure names are descriptive yet concise.

### Pull Request (PR)
- **One reviewer** might be selected for each PR. This reviewer is responsible for suggesting changes, providing feedback, and ultimately approving the PR.
- **One or more assignees** can be:
  1. Pull Request Author
  2. Author working on PR change suggestions 
  3. Person responsible to merge 


### README
All README.md files must align with [README Template](README_template.md) to ensure uniformity and detail across projects. 

Contributors should update these files to mirror significant changes such as new features, bug fixes, or changes in maintainers in time. While regular reviews are recommended to keep documentation accurate, feel free to adjust the template to better fit the project's needs.

### Versioning
Based on [Semantic Versioning 2.0.0](https://semver.org/). Version numbers are formatted as MAJOR.MINOR.PATCH, where:
- MAJOR versions indicate incompatible API changes
  - Hardware changes
- MINOR versions add functionality in a backward-compatible manner
  - Adding new LCM messages to mbot_lcm_base
- PATCH versions include backward-compatible bug fixes
  - Fixing edge cases found during the semester


### Releasing
Pre-Release Steps
1. **Versioning**: Finalize the version number based on the changes since the last release.
2. **Code Freeze**: Use "Lock branch" feature on GitHub to freeze the release branch before the planned release to stabilize the codebase. 
3. **Documentation**: Update documentation and README to reflect any changes, new features, or deprecations.

Release Process

1. **Changelog**: Update the changelog with a detailed list of changes, new features, bug fixes, and any known issues.
2. **Tagging**: Tag the release with the version number. If target is branch `release/1.0.0` the tag should be `v1.0.0`.
3. **Release Notes**: Include any special instructions or noteworthy information that relevant parties, such as classes or teams using the codebase, need to be aware of.


### Guidelines for Migrating to GitLab
New Repository
- For entirely new repository, download the current release from GitHub and upload it to GitLab.

Updating an Existing Branch
- Add the GitHub repository as a remote branch to your local repository.
- Push the desired release branch from GitHub to GitLab.
- Merge the changes into the main branch on GitLab.
