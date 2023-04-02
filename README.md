# compare-prod-and-stage-tags
Compare two tags between stage and prod releases. Error if they have source code changes

## Usage

```yaml
pre-deploy-prod:
    name: Prod - Deploy Checks
    if: (github.event_name=='workflow_dispatch')
    runs-on: [ self-hosted, linux, X64 ]
    steps:
      - name: Compare tags
        id: compare-tags
        uses: delfidiagnostics/compare-prod-and-stage-tags@v1.0
        with:
          prod_tag: ${{inputs.prod_tag}}
          stage_tag: ${{inputs.stage_tag}}
```