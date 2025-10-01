# PDS4 Context Product Management
This repository is for managing the **latest versions** of all PDS4 Context Products across NASA and IPDA archives. It is also the primary conduit for submitting updates to existing context objects, proposing new context objects, and filing issues on existing context objects.

- [Overview](#overview)
- [Raising Issues](#raising-issues)
- [Contributing Updates and New Products](#contributing-updates-and-new-products)
  - [To Request a New or Updated Context Product](#to-request-a-new-or-updated-context-product)
  - [To Create a New Context Product](#to-create-a-new-context-product)
  - [To Update an Existing Context Product](#to-update-an-existing-context-product)
  - [Updating Collection Files](#updating-collection-files)
- [Governance](#governance)
  - [Investigation LID Prefix](#investigation-lid-prefix)
  - [Instrument Host LID Prefix](#instrument-host-lid-prefix)
  - [Instrument LID Prefix](#instrument-lid-prefix)

## Overview
 At the IPDA Steering Committee meeting of September 2024, a need was identified for more transparency and better communication regarding the context products that are being created and used across PDS4-based systems in order to avoid duplication and to encourage best practices and collaboration. This repository was established in response to that finding.

**This repository contains only the latest version of each context product. The full, official archive, containing all versions, is curated by the PDS Engineering Node at https://pds.nasa.gov/data/pds4/context-pds4/.**

## Raising Issues

Any GitHub user can raise an issue in this repo. 

Common reasons for raising issues include:
- To request a new context product be created
- To request a modification to the content of an existing context product
- To report a problem noted in an existing context product

For tracking purposes, you should raise an issue even if you plan to do the work yourself. This helps ensure that development is visible to others who might be interested.

Discussion and collaboration on proposed additions and changes happens in the comment thread associated with each issue. 

## Contributing Updates and New Products

If you are planning to make modifications or submit a new context product yourself, here's the workflow:
1. Raise an issue in the NASA-PDS repo if one does not already exist.
2. Fork the NASA-PDS repo into your own GitHub account space to create a working copy.
3. In your working copy of the repo, create a branch with a name that contains the issue 
number(s) of the related issue(s)
4. Edit the branch of your working repo.
5. When you're done, file a Pull Request (PR) in the [NASA-PDS4/pds4-context-products]
(https://github.com/NASA-PDS/pds4-context-products/pulls) repo to request that EN merge the 
branch from your working copy into the NASA-PDS repo.

EN will take it from there.

Details of each step, including information on using the GitHub text editor, the GitHub 
Desktop app, and the git Command Line Interface(CLI) to make and publish changes, are 
provided in [Creating and Submitting Changes to the NASA-PDS Context Product Repo](EditSBS.md).

### To Request a New or Updated Context Product
When you need a new context product, or need updates to an existing context product: 
1. Create an issue in the NASA-PDS repository requesting the addition/change. 
Here's a handy link directly to the right "New issue" button: [New issue](https://github.com/NASA-PDS/pds4-context-products/issues/new/choose). 
2. Select "New Context Product Request" for a new product or "Update Context Product Request" 
for a modification, and fill in the form that pops up. 
Include whatever details you have. Do check before raising the issue that someone else hasn't 
already made the same request by checking [the current issues list](https://github.com/NASA-PDS/pds4-context-products/issues).
3. Click the green "Create" button in the lower right corner of the form to submit the 
request.
4. If you expect discussion, or want to get an email notice if someone comments, go back to 
[the current issues list](https://github.com/NASA-PDS/pds4-context-products/issues) and
click on the title of the issue you just submitted. At the bottom of the right column, there
is a "Subscribe" button. Click it to either subscribe or unsubscribe from notifications.

If you are not planning to create or update the context product yourself, you're done (though 
you may be contacted to answer questions or review the product someone else creates for you). 
If you are planning to create/update the product yourself, read on.  

### To Create a New Context Product

You will need to consult the [Guide to PDS4 Context Products](https://pds.nasa.gov/datastandards/documents/context/PDS4_Context_Products_Guide.v3.pdf) for 
logical identifier (LID) formation rules and the related file naming conventions. These 
vary slightly depending on the type of the context product you're creating. Inspecting
a few existing context products of the same type should help to clarify the instructions.
Pay particular attention to ```<type>``` fields, which are often incorporated into file 
names.

For both LIDs and filenames, make a reasonable guess and then post it in the comments
for the related issue, tagging Richard Chen (@rchenatjpl) to ask for a quick review. *EN 
personnel will adjust the LIDs and filenames if needed*, so checking with EN early on 
this point can save the effort of having to change these parameters in any data products you 
might be creating while the new context products are being reviewed. 

The items you need to address to create a new context product are:
- Determine the type of the context product you will create. If in doubt, ask Richard Chen 
(@rchenatjpl) in the issue comments.
- Determine the LID and filename you will use to submit the new product.
- Make sure the file name ends in "_v1.0", with a file extension of ".xml".
- Create the new context product in the corresponding context type folder (a new instrument 
goes in the *context-pds4/instrument* folder, a new mission goes in the *context-pds4/
investigation* folder, etc.). Make sure to use the full file name with the version number and 
extension. 
- Follow the [Guide to PDS4 Context Products](https://pds.nasa.gov/datastandards/documents/context/PDS4_Context_Products_Guide.v3.pdf) 
for including association and other aspects of content specific to the context type. 
- Validate the context product using the *Validate Tool*, if possible.

In addition to creating the context product itself, you will also need to update the 
corresponding collection product. See [Updating Collection Files](#updating-collection-files), below.

Details for working in GitHub to make these changes are covered in [Creating and Submitting
Changes to the NASA-PDS Context Product Repo](EditSBS.md).

### To Update an Existing Context Product

You must not change either the logical identifier (LID) or file name root when updating an 
existing context product. Depending on the updates needed, you may need to consult the
[Guide to PDS4 Context Products](https://pds.nasa.gov/datastandards/documents/context/PDS4_Context_Products_Guide.v3.pdf) for content details.

When updating an existing Context Product, follow these steps:
- Locate the current version of the product in the *context-pds4* type folder (an instrument 
will be in the *context-pds4/instrument* folder, a mission will be in the *context-pds4/
investigation* folder, etc.).
- Rename the existing file ***only**8to increment the version number at the end of the file name. 
Increment the minor version for a minor change, the major version for a major change.
- Edit the renamed file. The first changes you should make are:
  - Increment the ```<version_id>``` to match the version in the file name.
  - Add a new ```<Modification_Detail>``` to the ```<Modification_History>``` to document
  the changes being made.
- Make whatever additional changes are needed.
- Save the file.  
In addition to editing the context product itself, you will also need to update the 
corresponding collection product. See [Updating Collection Files](#updating-collection-files), below.

Details for working in GitHub to make these changes are covered in [Creating and Submitting Changes to the NASA-PDS Context Product Repo](EditSBS.md).

### Updating Collection Files

When any change is made to a *context-pds4" folder, corresponding changes will be required in 
the collection inventory and collection label files. Collection product labels will begin with *collection_* and end with *.xml*. Collection inventory files will have the same name as 
the label, with an extension of *.csv*.

***SHOULD GENERAL CONTRIBUTORS BE DOING THIS?*** 

## Governance
With most context products originating from a parent investigation, the lead agency of an investigation governs over the context products that fall under that investigation. Creation and management of context products related to an investigation can be delegated to other affilliated agencies through collaboration and discussion.

For context products that do not originate from an investigation (e.g., a target context product), the agency who identifies and creates the context product will gain ownership over that context product.

### Investigation LID Prefix
LID prefix for the lead agency. If there is not a clear lead agency, then this is determined via discussion amongst the affiliated agencies.

### Instrument Host LID Prefix
LID prefix for the Instrument Host lead agency. If there is not a clear lead agency, then this is determined via discussion amongst the affiliated agencies.

### Instrument LID Prefix
LID prefix for the Instrument lead agency. If there is not a clear lead agency, then this is determined via discussion amongst the affiliated agencies.


