# How to craft an integration flow recipe

> [!IMPORTANT]
> Any Intellectual Property (or Business Secret) relevant material should __**not**__ be posted here. All commits are in the "public domain". If your best practice gets merged to the repo after a review by our governance team, you will be credited. You can also be a part of this governance team once at least one meaningful contribution was accepted.

## Before you start

1. Ensure Intellectual Property safety. Be sure to publish original content that does not belong to or have references to intellectual property belonging to your employer, customer, partner or anyone else.

1. Ensure you have read SAP's [Integration Flow Design Guidelines | help.sap.com](https://help.sap.com/docs/cloud-integration/sap-cloud-integration/integration-flow-design-guidelines) and your sample code complies with these guidelines.

## You will need

1. An integration scenario, which could be:
    1. A frequent question with an SAP Integration Suite or Azure artifact as an answer.
    1. A blog you wrote with code in it.
    1. A topic requested by the community in the [issues](https://github.com/Azure-Samples/Sentinel-For-SAP-Community/issues)
2. A git hub user. If you need one, [sign up here](https://github.com/join)
3. A [git client](https://git-scm.com/downloads).

## Recipe for writing recipes

Step|Action|Description
----|----|----
Fork the repo | [how to fork a repo?](https://help.github.com/en/articles/fork-a-repo) | Forking the repo creates a copy of the repo in your account. You have full control over this forked repo. Changes to the forked repo can be pulled into the original repo.
Create recipe folder |  Folder path should be '_integration-artifacts/[your-artifact-type]/**your scenario name**/_' | In your forked repo, create a folder to put all content relating to the recipe. *(Tip: Best folder names that look like \<verb\>-\<object\> )*  |
Copy all supporting artifacts | | Copy everything that you need for your recipe in the folder. Some files you should consider uploading are integration flow zip files, sample input or output files, screenshots (of integration flow layout (the BPMN diagram), input screen, output screen, code snippets) etc. *(Tip: you can always come back and add more files if you forgot some.)* |
Create readme.md file | Copy [readme.md template](integration-artifacts/solution-packages/) and save to file named README.md | Add your content. *(Tip:  most editors have a markdown previewer where you can see how your recipe will look while you update the readme.md; for Atom use CTRL+SHIFT+M to invoke previewer )*  |
Commit, Push| | Submit content into your forked repo|
Submit a pull request | [creating a pull request from a forked repo](https://help.github.com/en/articles/creating-a-pull-request-from-a-fork) | |
Keep your fork synced | [Keep your fork updated with master](https://help.github.com/en/articles/fork-a-repo#keep-your-fork-synced) | If you need to update your recipes at a later date, it helps to keep your fork synced so that you can submit without any merge conflicts.
