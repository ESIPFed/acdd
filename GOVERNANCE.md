# Governance
The ACDD Steering Committee formalizes changes and additions to ACDD.

The discussion for changes to ACDD is carried out via this wiki and the [ESIP Documentation Cluster mailing list](http://lists.esipfed.org/mailman/roster/esip-documentation). 
To sign up for edit privileges for this wiki you must first [register at the ESIP Commons](http://commons.esipfed.org/user/register). This registration also 
grants access to other community resources supported by ESIP. Both the mailing list and this wiki are open and 
anyone in the community. ACDD will evolve based on the discussions on this list and as documented on these wiki 
pages. Occasionally, the discussion may need to be moderated or a decision must be made. In these cases the 
steering committee will vote and adopt a solution as described below.

## Steering Committee

ACDD will evolve based on the direction of the steering committee, which is comprised of the following members:

* Anna Milan (Co-chair) NGDC
* John Graybeal (Co-chair) Graybeal.SKI Consulting
* Dave Blodgett USGS
* Nan Galbraith WHOI
* Ted Habermann The HDF Group
* Steve Hankin PMEL
* Marcos Hermida Unidata
* Aleksandar Jelenak The HDF Group
* Anna Milan NGDC
* Dave Neufeld CIRES
* Rich Signell USGS
* Bob Simons NMFS
* Derrick Snowden IOOS
* Ed Armstrong JPL

## Decision Making Process

Vote 70% majority of voting members; members may decline to vote on some issues

If a vote is taken or a decision is reached, that decision should be broadcast to those who could not be present. 
Discussion of the decision takes place for some period of time (or till the next meeting?) If there is disagreement 
or ongoing discussion, the decision is not finalized. If there is no discussion or disagreement, the topic is final 
and will not be revisited later.

## Governance (following CF Convention Rules for Modifying Standard Names)

New proposals are made by opening a new issue in the [acdd GitHub repository](https://github.com/ESIPFed/acdd).
The 'Standard Names' template should be used, even if the proposal relates to one of the other vocabularies.

Proposals may be for:
- new term(s) to be added;
- change to existing term(s) i.e. creation of alias(es)
- clarification/correction of description or units of existing term(s).

The discussion will be moderated by the standard names secretary, or another person familiar with the information management procedures for maintaining the published vocabularies.

The discussion takes place on GitHub issues and all may participate.

A status page summarizing the progress of proposals through the discussion process may also be viewed in the
[CEDA vocabulary editor](https://cfeditor.ceda.ac.uk/proposals/1).

If a proposal is received for a new vocabulary term that follows the same syntactic patterns as existing terms, and whose description can also be based on existing term descriptions, the proposal can be accepted after brief discussion, subject to checking by the moderator.

For proposals that require more discussion, the moderator periodically summarises the current status on github, keeps it moving forward and tries to achieve a consensus.
It is expected that everyone with an interest will contribute to the discussion and to achieving a consensus during this stage.
During the discussion, if an objection is raised, answered and not reasserted, the moderator will assume the objection has been dropped.
However, since consensus is the best outcome, it will be helpful if anyone who expresses an objection explicitly withdraws it on changing their mind or deciding to accept the majority view.

If a consensus, or near consensus, view can not be achieved by discussion the moderator can ask the standard names committee to vote on a proposal.
The committee's decision is final.

If 30 days have passed with no contributions being made the moderator should attempt to reinvigorate the discussion so that a conclusion can be reached.

The moderator will summarize the outcome of the discussion of each vocabulary term proposal.

A proposal will be accepted if one of the following is true:
- it is similar to existing terms and has been checked for conistency by the moderator;
- consensus has been reached in favour of the proposal;
- the moderator's summary indicates that consensus in favour of the proposal has nearly been achieved;
- a majority of the standard names committee vote to accept the proposal.

A proposal will be rejected if one of the following is true:
- it duplicates an existing vocabulary term;
- consensus has been reached against the proposal;
- the moderator's summary indicates that consensus against the proposal has nearly been achieved;
- a majority of the standard names committee vote to reject the proposal;
- the proposer withdraws the proposal;
- the change is not backwards-compatible with previous versions of the ACDD.

The published vocabularies are updated approximately every 1 - 2 months.
The publication date will be announced ahead of time via a github issue.
Any names that have been formally accepted will be included in the next update, thus the period between acceptance and publication may vary from a few weeks to as little as a day.

The author of an accepted proposal should be added to the
[list of standard name contributors](http://cfconventions.org/Data/cf-standard-names/docs/standard-name-contributors.html).

All versions of the ACDD 1.3 should be kept available online, and for ACDD 1.3.X onward should also include their github discussion issues.

The workflow associated with standard name proposals is summarized in the diagram below.
![Schematic representation of how standard names are processed using github issues and the vocabulary editor.](https://github.com/cf-convention/cf-convention.github.io/blob/main/Data/media/images/cf-standard-names-process.png)

These rules were modified from those of the CF Conventions (https://cfconventions.org/standard_name_rules.html) and we thank those contributors.
