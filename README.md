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
Dette gjøres ved å først commite og pushe endringene, og deretter tagge med ny versjon:

```bash
 > git tag -a -m "Ny og bedre" v1.1.1                                                                                                       128 ✘  10:53:36 

 > git push --follow-tags                                                                                                                       ✔  10:53:45 

Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 166 bytes | 166.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:navikt/pia-actions.git
 * [new tag]         v1.1.1 -> v1.1.1
```
---

# Henvendelser

Spørsmål knyttet til koden eller prosjektet kan stilles som issues her på GitHub

## For NAV-ansatte

Interne henvendelser kan sendes via Slack i kanalen [#team-pia-utvikling](https://nav-it.slack.com/archives/C02T6RG9AE4).

## Kode generert av GitHub Copilot

Dette repoet tar i bruk GitHub Copilot for kodeforslag.