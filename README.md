# lllIIIIlll GitHub Actions

Custom GitHub Actions for lllIIIIlll.

**When using these workflows, please consider whether you want to freeze the version of the workflow (more stability), or always use the latest available. Refer to [GitHub documentation](https://docs.github.com/en/actions/using-workflows/reusing-workflows#calling-a-reusable-workflow) for more details.**

Many of these actions make use of the `github.token` input as well as `NEXUS_USER` and `NEXUS_PASSWORD` secrets. The first is provided automatically by GitHub Actions, and the NEXUS secrets are available for all repositories within the lllIIIIlll GitHub organisation. and should not need to be set manually.

```yaml
# Using latest by tagging @main
uses: lllIIIIlll/actions/sonar-scan@main

# Using a specific version by commit hash
uses: synpulse-group/s8-actions/sonar-scan@69107d51121e3346385fe6d8e17bb2e92bdfe0fe
```

---

## `sonar-scan` (on pull request and push)

<details>
  <summary>Expand</summary>

### What does it do?

This Action enables Sonar scan on a PR. Sonar scans the code smells, code coverage, code duplication and securiy hotspots of the PR.

### Inputs and their defaults

| Name | Description | Mandatory? | Default |
| --- | --- | --- | --- |
| `sonar-token` | Sonar token for authentication | yes | |
| `nexus-user` | Nexus user for authentication | yes | |
| `nexus-password` | Nexus password for authentication | yes | |
| `java-version` | Java SDK version | no | 17 |
| `java-distribution` | Java SDK distribution | no | zulu |

### Things to note

- Before enabling this workflow, please create a project in [SonarCloud](https://sonarcloud.io/projects) and disable the automatic analysis in your sonar project.
- Setting up Sonar correctly in your project is also required before running sonar scan workflow.

### Sample usage

See [example usage](./examples/sonar-scan/sample.yml) for a full workflow example.

</details>

---