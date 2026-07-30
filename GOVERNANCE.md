# Contributing to the Attribute Convention for Data Discovery (ACDD)

Thank you for your interest in the [ACDD](https://wiki.esipfed.org/Attribute_Convention_for_Data_Discovery_1-3/).

The following guidance for contributing and governance rules are modelled after the [CF conventions](https://github.com/cf-convention/cf-conventions/blob/main/CONTRIBUTING.md).

As a prerequisite to getting involved, please review the community's code of [conduct](https://github.com/ESIPFed/acdd/blob/main/CODE_OF_CONDUCT.md).

These rules are designed to make it easy to contribute to the ACDD and are tailored to GitHub, the platform where they are hosted.
They are intended to support your work and not to constrict you; if at any time you find them difficult to follow, please ask for help.

## Contents

* [Rules for Changes to the ACDD](#rules)
  * [Versions and schedule for updating the ACDD conventions](#new_versions)
  * [Rules for enhancements to the ACDD conventions](#enhancement_rules)
  * [Dormant issues](#dormant_issues)
* [Technical guidelines](#technicalities)
  * [Pull requests](#pull_requests)
  * [Text styling](#text_styling)
* [Revision history of the rules](#history)

## Rules for changes to the ACDD

These rules apply to the ACDD conventions and related documentation.
They describe the practices and procedures that should be used in fixing, updating, or adding to the metadata attributes.

All changes to the ACDD should be discussed on GitHub using a consensus model for adoption. Each change should be initiated in an [issue](https://github.com/ESIPFed/acdd/issues). If there is support, then the change should be summarized and a pull request created. See [ Rules for enhancements to the ACDD conventions] (#rules-for-enhancements-to-the-acdd-conventions)


All changes to the conventions documents are proposed and discussed in an [issue](https://github.com/ESIPFed/acdd/issues) and implemented in a related [pull request](https://github.com/ESIPFed/acdd/pulls) in the [ACDD conventions GitHub repository](https://github.com/ESIPFed/acdd/), which contains the source of the ACDD conventions documents.

----

### How to suggest changes

Submit requests for changes to the ACDD [github repository](https://github.com/ESIPFed/acdd). Use the template for a new issue.

Issues are organized into the following categories:

label | description
------|-------------
enhancement | add new capabilities or improve existing ones
defect | corrections to substantial defects
copy edit | (spelling mistakes, etc)

In the template, please indicate which category of change you are suggesting and we will apply the appropriate label.

Submitters of suggested changes may be added to the contributors list.

----

### Versions and schedule for updating ACDD

New versions of the conventions are published as needed, following the [semantic versioning](https://semver.org/) schema. 
  

All previously published versions of the conventions will be available as releases in GitHub.

----

### Rules for enhancements to the ACDD conventions


Identified a problem
Make an issue
Issue will be available for open discussion for any interested participants
Issues can be closed under the following conditions:
Once consensus is reached, the issue can be closed and move to summary and Pull Request
After no activity in the issue for 3 months, an automated message will prompt administrators to take some action on the issue (close, raise for more discussion, merge, leave open, etc.). After three additional months it will become a [dormant issue](link below).
After no discussion for one week the issue will be closed or implemented according to the consensus reached. 
Some admin will describe the final decision and propose the changes as a Pull Request or instruct someone else to propose the changes. 
Pull Request will be merged after final review period of one week.
If there are objections, a new issue can be opened.

When closing issues administrators should provide a brief description of why the issue is being closed.

The moderator is encouraged to organize discussion meetings if this might help resolve an issue more quickly.

The arguments presented and any conclusions reached in such a meeting should be summarised afterwards in the GitHub issue, for the record and so that everyone can continue to be involved in further discussion.

In case of any disagreement, the conventions committee will arbitrate.

----

### Dormant issues

If an issue falls silent for more than six months without conclusion, any member of the ACDD steering committee may post on the issue to encourage any interested person to resume it within three weeks, if they wish it to remain open.
If discussion does not resume within three weeks, the issue should be closed with the `dormant` label attached.
The issue may subsequently be reopened and the `dormant` label removed by anyone wishing the continue the discussion.


### Pull requests

Pull requests should be submitted to the `main` branch of the repository.
Use of other branches is at the discretion of the repository administrators.
It is recommended that pull requests are created on a branch of a personal fork of the repository.
Comments in pull requests should be avoided, unless discussing changes to the wording of a proposal that do not impact on the agreed meaning.

----

### Text styling

The ACDD documents and website are generated from a mix of AsciiDoc and Markdown files.
The files should be formatted in line with the
[AsciiDoc Recommended Practices](https://asciidoctor.org/docs/asciidoc-recommended-practices/)
and
[Google Markdown style guide](https://google.github.io/styleguide/docguide/style.html).
Each sentence should begin on a new line.


----

## Revision history of the rules

* This document was created (commit link)

