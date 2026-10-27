# chef-repo

This repository contains configuration files and cookbooks for managing infrastructure using Chef or Cinc.

## Structure

This is a large monorepo with (mostly) Ruby-based DSL Chef code. The main directories and files are:

- `.chef/`: Directory for Chef configuration files. Your API key should be placed here. `.cinc` is a symlink to this directory for compatibility.
- `code_generation/`: Directory for scripts (many of which don't actually generate code).
- `cookbooks/`: Directory containing Chef cookbooks. Each cookbook subdirectory contains:
  - `attributes/`: Default values and settings.
  - `Berksfile`: Dependency management file (used when testing in kitchen).
  - `CHANGELOG.md`: Version history for the cookbook.
  - `files/`: Static files referenced by recipes and resources.
  - `files/audit/`: InSpec controls (tests).
  - `.kitchen.yml`: Configuration for Test Kitchen (an ERB template that compiles to YAML).
  - `libraries/`: Helper Ruby code to be used in recipes and resources.
  - `metadata.rb`: Cookbook dependencies and version.
  - `README.md`: Documentation for the cookbook.
  - `recipes/`: Configuration code (Ruby DSL) - the actual functionality of the cookbook.
  - `resources/`: Custom resources (reusable configuration components).
  - `templates/`: ERB templates for generating files with variables.
- `environments/`: Directory for environment configurations.
- `roles/`: Directory for Chef roles.
- `.rubocop.yml`: Configuration file for `cookstyle` linting tool.

## Rules for Contributing

See the [CONTRIBUTING.md](CONTRIBUTING.md) file for guidelines on how to contribute to this repository.

## Testing

See the [TESTING.md](TESTING.md) file for instructions on how to test changes made in this repository.
