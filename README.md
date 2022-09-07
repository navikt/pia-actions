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

---

# Henvendelser

Spørsmål knyttet til koden eller prosjektet kan stilles som issues her på GitHub

## For NAV-ansatte

Interne henvendelser kan sendes via Slack i kanalen [#team-pia-utvikling](https://nav-it.slack.com/archives/C02T6RG9AE4).

