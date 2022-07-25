# Authoring guidelines

## Module structure

Modules should adhere to a common [module structure](module-structure.md).

## Module names

Module repositories for IBM Cloud must use the three-part name format `terraform-ibm-<NAME>` where `<NAME>` reflects the type of infrastructure that the module manages.
Use hyphens in `<NAME>` as delimiters for multiple strings (for example, `activity-tracker`).

Provide a short one-line description of the primary module in the repository. The description is displayed under the repository title on the [organization page](https://github.com/terraform-ibm-modules) and in the **About** section of the repository. Use the description to help users understand what your repo does by looking at the description.

### Nested module names

Do not repeat the name of the top-level module in nested modules. For example, for a top-level module that is named `terraform-ibm-cos`, do not name the nested module `cos-instance` because it converts to "cos_cos-instance" in the module registry. Use `instance` (to register the child-module as "cos_instance") instead.

## Module variables

### Variable names

Input and output variable names must correspond to the names used in the IBM Cloud UI, CLI, or in the IBM Cloud Documentation.

### Variable descriptions

Input and output variables should have a short description in the `variables.tf` and in `README.md` file. Description should be full English sentences. Avoid using abbreviations.

?> **Tip**: The variable names and description in the readme file at the root of the repo are generated by [pre-commit hooks](https://github.com/terraform-ibm-modules/common-dev-assets/blob/main/module-assets/.pre-commit-config.yaml#L28). The values come from the `variables.tf` file.

### Variable defaults

Include default values where possible and set the sensitive flag as needed. Update the meaning of a type only with agreement of the governance body.

## Module examples

[inc-examples](inc-examples.md ':include')

## Module validation tests

Modules must contain at least one automated validation test that runs Terraform apply and destroy commands, and tests the idempotency of the module. See [Validation tests](tests.md) for details.

## Commit messages and versioning

Use [Conventional Commit](https://www.conventionalcommits.org) messages when you commit code.

- Conventional commits determine whether a new version of a module is needed and which semantic versioning number to use. As a module author or contributor, you don't need to release a new version. When a PR is merged into the main branch, a new release is created by the release automation if the validation pipeline passes.
- The commit messages are published in the release notes for the module.
- For more information, see this handy [cheat sheet](https://cheatography.com/albelop/cheat-sheets/conventional-commits/).

[Git tags](https://git-scm.com/book/en/v2/Git-Basics-Tagging) are used to identify module versions. Release tags are based [semantic version](https://semver.org/) guidelines. For example, v1.0.0.

## Module documentation

Document the module in the readme file at the same level as the `main.tf` file for each of the modules in a repository, including the example modules. Put content that isn't required initially in a `docs` subdirectory.

For consistency across modules, all `README.md` files should follow the same structure. See the [README.md template](https://github.com/terraform-ibm-modules/terraform-ibm-module-template/blob/main/README.md).