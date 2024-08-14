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
  trivy-scan:
    name: Scanner docker image med Trivy
    needs: build
    permissions:
      contents: read # to write sarif
      security-events: write # push sarif to GitHub security
      id-token: write # for nais/login
    runs-on: ubuntu-latest
    steps:
      - uses: navikt/pia-actions/trivy-scan@v1 # https://github.com/navikt/pia-actions/tree/main/trivy-scan
        with:
          image: ${{ needs.build.outputs.image }}
          team: pia
          project_id: ${{ vars.NAIS_MANAGEMENT_PROJECT_ID }}
          identity_provider: ${{ secrets.NAIS_WORKLOAD_IDENTITY_PROVIDER }}
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