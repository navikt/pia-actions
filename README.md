pia-actions
================

Gjenbrukbare actions for Team Pia, til bruk i interne workflows i andre repoer 

# Komme i gang

Actions i dette prosjektet kan tas i bruk ved å importere de i en annen workflow. Som for eksempel slik:

```yaml
name: Din nye kule workflow

on:
  push:
    branches:
      - main

jobs:
  e2e-tests:
    runs-on: ubuntu-latest
    steps:
      - uses: "navikt/pia-actions/forebyggingsplan-e2e@v1.0.1"
        name: "e2e-tester for forebyggingsplan"
```

# Ved oppdatering av actions

Når man har gjort endringer i noen av disse actionene, må man huske på å tagge med ny versjon.
Dette gjøres ved å først commite og pushe endringene, og deretter tagge med ny versjon, og oppdatere v1 taggen.

```bash
git tag -a -m "Hva som er gjort" v1.1.4
git push --follow-tags
git tag -fa v1 -m "Update v1 tag"
git push origin v1 --force
gh release create v1.1.4
```
---

# Henvendelser

Spørsmål knyttet til koden eller prosjektet kan stilles som issues her på GitHub

## For NAV-ansatte

Interne henvendelser kan sendes via Slack i kanalen [#team-pia-utvikling](https://nav-it.slack.com/archives/C02T6RG9AE4).

## Kode generert av GitHub Copilot

Dette repoet tar i bruk GitHub Copilot for kodeforslag.