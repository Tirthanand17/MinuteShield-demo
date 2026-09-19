# MinuteShield Demo

This repository is a small public example showing how to install and validate [MinuteShield](https://github.com/Tirthanand17/MinuteShield), a GitHub Action that estimates GitHub Actions cost regressions before merge.

## Installed version

The demo workflow uses the published release:

```yaml
uses: Tirthanand17/MinuteShield@v0.1.0
```

See `.github/workflows/minuteshield.yml` for the complete installation example.

## Real validation

A controlled pull request added a macOS matrix workflow that was permanently skipped at runtime, so no macOS runner minutes were consumed. MinuteShield still analyzed the YAML and posted a sticky PR report identifying:

- macOS runner usage
- missing `timeout-minutes`
- missing `concurrency.cancel-in-progress`
- estimated monthly GitHub Actions cost delta

Demo PR: https://github.com/Tirthanand17/MinuteShield-demo/pull/1

## Links

- MinuteShield: https://github.com/Tirthanand17/MinuteShield
- Live calculator/site: https://tirthanand17.github.io/MinuteShield/
- v0.1.0 release: https://github.com/Tirthanand17/MinuteShield/releases/tag/v0.1.0

MinuteShield produces preventive estimates, not GitHub invoices. Actual billed cost depends on repository visibility, included usage, runner type, execution time, and account plan.