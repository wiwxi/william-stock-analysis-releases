# William Stock Analysis

A standalone skill package for in-depth equity research. Current public release: **2.2.0**.

**[Download the installation package](https://github.com/wiwxi/william-stock-analysis-releases/releases/latest/download/william-stock-analysis.tar.gz)** · **[Release notes and checksums](https://github.com/wiwxi/william-stock-analysis-releases/releases/latest)**

## What's included

- 14 William Stock Analysis skills and the bundled `humanizer-zh` editorial skill.
- An eight-section investment report, with business model and stakeholder analysis, financial and risk analysis, and supporting visuals.
- Scenario valuation, a quantitative margin of safety, a recalculable workbook interface, and an independent review workflow.
- The installer, runtime, templates, methodology, tests, and licenses.

The download includes the skills and their supporting files. It requires no access to another repository. Research reports, private notes, account credentials, and paid data access stay with their owners.

## Install with an AI assistant

Download and extract the archive to get the `william-stock-analysis/` directory. Give the directory to an assistant that supports local skills and ask:

> Read the package README and installation instructions. Identify the persistent skills directory used by this assistant. Verify the hashes in manifest.json and preview installation with installation/install.py. Apply only when the preview is limited to package-owned files and preserves unrelated skills and manual edits. Then verify all 14 William skill entry points and the bundled humanizer-zh, and report the dependencies and any limits of this host.

Persistent installation requires a host that supports local `SKILL.md` files and can run the installer. Network access depends on the host.

## Install from the command line

Use Python 3.11 or later. Download and verify the archive in an empty directory.

```sh
curl -fL -o william-stock-analysis.tar.gz https://github.com/wiwxi/william-stock-analysis-releases/releases/latest/download/william-stock-analysis.tar.gz
curl -fL -o SHA256SUMS https://github.com/wiwxi/william-stock-analysis-releases/releases/latest/download/SHA256SUMS
shasum -a 256 -c SHA256SUMS
tar -xzf william-stock-analysis.tar.gz
cd william-stock-analysis
```

On Linux, use `sha256sum -c SHA256SUMS` if `shasum` is unavailable. Set the path to the skills directory your assistant actually uses.

```sh
STOCK_SKILLS_ROOT="/absolute/path/to/your/skills"
python3 installation/install.py --package . --manifest manifest.json --root "$STOCK_SKILLS_ROOT"
python3 installation/install.py --package . --manifest manifest.json --root "$STOCK_SKILLS_ROOT" --apply
PYTHONPATH="$STOCK_SKILLS_ROOT/william-stock-analysis/package/runtime" python3 -m william_stock capabilities
```

The first installer command previews changes. The second applies them. Confirm that your host discovers the new entries before using them. Creating and recalculating workbooks requires the dependencies listed in the package and a working spreadsheet engine, such as LibreOffice. Use your own model and authorized data sources.

## Example request

> Use william-stock-analysis to research the stock I specify. In eight sections, explain the investment judgment, business model, shareholder returns, industry context, market pricing, downside risks, buy conditions, and supporting evidence. State the data cutoff, show scenario prices, and quantify the margin of safety.

Research quality depends on the evidence and the capabilities available to the host. The package makes no promise about returns or forecast accuracy.

## Version and integrity

Version 2.2.0 standardizes the opening valuation table at six columns and cross-checks every cell against the delivered Markdown and workbook formulas. It also includes the evidence-gap checks and conditional buy ceilings introduced in 2.1.0, plus single-stock screening, batch aggregation, full research, and periodic thesis reviews.

Archive SHA-256:

```text
3217b8835a22fc06b30dfc5ff0c6b2741710e2943fde623b7529f128581e7c68
```

For a pinned version, use [v2.2.0](https://github.com/wiwxi/william-stock-analysis-releases/releases/tag/v2.2.0).

## License

See [LICENSE](LICENSE) and [NOTICE](NOTICE) for the package terms and third-party attributions. The public download grants only the rights stated in those files.
