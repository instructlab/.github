# Welcome to the 🐶 InstructLab Project

<p align="center">
<img src="https://github.com/instructlab/.github/blob/main/assets/instructlab-banner.png">
</p>

InstructLab 🐶 uses a novel synthetic data-based alignment tuning method for Large Language Models (LLMs.) The "lab" in InstructLab 🥼 stands for [**L**arge-Scale **A**lignment for Chat**B**ots](https://arxiv.org/abs/2403.01081) [1].

[1] Shivchander Sudalairaj*, Abhishek Bhandwaldar*, Aldo Pareja*, Kai Xu, David D. Cox, Akash Srivastava*. "LAB: Large-Scale Alignment for ChatBots", arXiv preprint arXiv: 2403.01081, 2024. (* denotes equal contributions)

## Why InstructLab

There are many projects rapidly embracing and extending permissively licensed AI models, but they are faced with three main challenges:

* Contribution to the models themselves is not possible directly. They show up as forks, which forces consumers to choose a “best-fit” model that isn’t easily extensible, and the forks are expensive for model creators to maintain.
* The ability to contribute ideas is limited by a lack of AI/ML expertise. One has to learn how to fork, train, and refine models in order to see their idea move forward. This is a high barrier to entry.
* There is no direct community governance or best practice around review, curation, and distribution of forked models.

## Unforking Models: The InstructLab Method

InstructLab is a project that enables a pull request-like upstream contribution acceptance workflow for models. These upstream contributions add additional "skills" or "knowledge" to the model ([read more about these in the `taxonomy` README](https://github.com/instructlab/taxonomy/blob/main/README.md).) These can be created by providing a much smaller number of "example" data artifacts than would normally be required to influence an LLM. (E.g., 5 samples instead of 5,000.) The technique involves using generative AI to create synthetic data to "expand" the limited data artifact set to a scale that would influence the model. This generated data is then used to instruct tune an LLM, effectively teaching it new skills or knowledge that it previously could not do, or did not do well.  This skill or knowledge can then be submitted upstream to the community, and if accepted, that contribution would be included in a new build of the model.

The way this technology has been built, it is not model-specific. IBM has already released two "lab-enhanced" (via InstructLab) models on HuggingFace:

* [Labradorite](https://huggingface.co/ibm/labradorite-13b) (lab-enhanced llama2)
* [Merlinite](https://huggingface.co/ibm/merlinite-7b) (lab-enhanced Mistral)

The technology gives model upstreams with sufficient infrastructure resources the ability to create nightly builds of their open source licensed models (again, not rebuilding / retraining the entire model, but composing just the new skills into it.) They would accept pull requests to their models; these PRs would then be included in the next nightly build.

Contributors that are currently creating their own forks of models like Mistral are now able to accelerate their work and avoid the costs of forking and retraining their models.  Once proven out, we expect this to attract an even broader set of contributors that have less AI expertise but have creative ideas on how to extend AI models.

---

## InstructLab is composed of the following projects

### [Taxonomy](https://github.com/instructlab/taxonomy)

The InstructLab method is driven by taxonomies, which are largely created manually and with care. This repository contains a taxonomy tree that will allow you to create models tuned with your data (enhanced via synthetic data generation) using the InstructLab method.

* [Repo](https://github.com/instructlab/taxonomy)
* [Contributing](https://github.com/instructlab/taxonomy/blob/main/CONTRIBUTING.md)

### [Command-line Interface](https://github.com/instructlab/instructlab)

This command-line interface for InstructLab will allow you to create models tuned with data you provide using the InstructLab method on your laptop or workstation.

* [Repo](https://github.com/instructlab/instructlab)
* [Contributing](https://github.com/instructlab/instructlab/blob/main/CONTRIBUTING/CONTRIBUTING.md)

> [!IMPORTANT]
> It is important to understand that running InstructLab on a laptop will give you a low-fidelity approximation of both synthetic data generation (using the `ilab generate` command)
> and model instruction tuning (using the `ilab train` command, which uses QLoRA.) The quality of the results you get using these tools on a laptop will not be as high-fidelity as they might be using
> a larger teacher model and a different training method. We have optimized InstructLab to enable community members with modest hardware to be able to use the technique. If you have more sophisticated
> hardware, you can configure InstructLab to use a larger teacher model [such as Mixtral](https://huggingface.co/docs/transformers/model_doc/mixtral) in order to achieve higher-fidelity results.
  
## Model Training Infrastructure

The infrastructure used to regularly train the model based on new contributions from the community is GPU intensive and generously donated and maintained by IBM.

---

<!--
## Additonal aspects of the project include:

- [community](): community content
- [github-bots](): automated CI/CD bots and related content
-->

### Code of Conduct & Covenant

Participation in the InstructLab community is governed by our [Code of Conduct & Covenant](https://github.com/instructlab/community/blob/main/CODE_OF_CONDUCT.md).

### Governance

How the InstructLab project [governance](https://github.com/instructlab/community/blob/main/governance.md) operates.

### Security

Security policies and practices, including reporting vulnerabilities can be found in our [Security.md](https://github.com/instructlab/community/blob/main/SECURITY.md).
