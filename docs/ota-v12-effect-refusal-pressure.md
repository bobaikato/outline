# Ota V12 Effect-Refusal Pressure

Status: fork-only, pre-release Ota pressure. This is not an upstream pull request, endorsement,
or proof that Outline is governed by Ota.

## Inputs

- upstream revision: `d8d8f2fffed97eaf3e9d48d820c8f1e1facf4008`
- fork branch: `bobai/v12-effect-refusal-pressure`
- Ota source: Core `cd99c9abd2c0225b454371e897eca2486319db26`, reporting v1.6.27
- migration root: `server/migrations`, bound to its exact content identity
- policy source: repository-controlled `.ota/org-policy.yaml`

## Exercised Surface

The Linux/macOS pressure workflow validates the contract, then challenges both the direct `db:migrate` task
and the `server-ci` workflow. The latter mirrors the committed Outline server-test CI lane's
Sequelize migration prerequisite before its `yarn test:server` command. Both controls must return
an explicit typed deny with `execution_started: false`.

The matrix does not start PostgreSQL, execute Sequelize or Yarn, contact a provider, or write a
migration. It proves only Ota's observed refusal of the exact selected migration realization under
this repository-controlled policy.

## Unproved Boundaries

- actual database mutation or correctness;
- provider authority, contact, or re-evaluation;
- independently administered policy authority;
- arbitrary child-process absence or repository-wide immutability;
- positive receipt, archive, export, or assurance;
- complete coverage of all Outline migration and deployment paths.
