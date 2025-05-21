# PDS4 Context Product Management
Repository for managing the latest versions of all PDS4 Context Products across NASA and IPDA archives.

- [Overview](#overview)
- [Contribute](#contribute)
  - [Update Process](#update-process)
  - [Propose New Context Product](#propose-new-context-product)
- [Governance](#governance)
  - [Investigation LID Prefix](#investigation-lid-prefix)
  - [Instrument Host LID Prefix](#instrument-host-lid-prefix)
  - [Instrument LID Prefix](#instrument-lid-prefix)

## Overview
Per IPDA Steering Committee meeting in September 2024, a need was identified for more clear transparency and communication with regard to current and future context products being used across the system in order to avoid duplication, and encourage best practices and collaboration.

**This repository contains only the latest versions of all PDS4 Context Products. The official archive, containing all versions, is curated by the PDS Engineering Node at https://pds.nasa.gov/data/pds4/context-pds4/.**

## Contribute

### Update Process

To update an existing context product, there are some important steps to complete in order to update the content and the version of the context product:

1. Use a `git move` or rename the file with the **new version number**. This is important to maintain revision history of the file. For example, if I am upgrade voyager v1.2 to v2.0:

```
git mv data/pds4/context-pds4/investigation/mission.voyager_1.2.xml  data/pds4/context-pds4/investigation/mission.voyager_2.0.xml
```

**If updating in the browser:**
<img width="1370" alt="Screenshot 2025-05-14 at 8 02 26 AM" src="https://github.com/user-attachments/assets/ea9786c9-5563-4402-a946-1ea2c9fe9848" />

**If updating using Git Desktop:***
TBD

2. Be sure to update the `version_id` in the label

3. Commit your changes

5. Push to a new branch

7. Create a pull request

### Propose New Context Product
1. Create a [new issue on this repository](https://github.com/NASA-PDS/pds4-context-products/issues)
2. Create a pull request with your new context product under the appropriate directory for your agency.
  1. If you are not familiar with creating pull requests, add the proposed context product to the ticket and request @jordanpadams to assist.

## Governance
With most context products originating from a parent investigation, the lead agency of an investigation governs over the context products that fall under that investigation. Creation and management of context products related to an investigation can be delegated to other affilliated agencies through collaboration and discussion.

For context products that do no originate from an investigation (e.g. a target context product), the agency who identifies and creates the context products will gain ownership over that context product.

### Investigation LID Prefix
LID prefix for the lead agency. If there is not a clear lead agency, then this is determined via discussion amongst the affiliated agencies.

### Instrument Host LID Prefix
LID prefix for the Instrument Host lead agency. If there is not a clear lead agency, then this is determined via discussion amongst the affiliated agencies.

### Instrument LID Prefix
LID prefix for the Instrument lead agency. If there is not a clear lead agency, then this is determined via discussion amongst the affiliated agencies.


