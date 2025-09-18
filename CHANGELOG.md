# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-09-18

### Added
- Initial release of Overmind Cost Signals Action
- Infracost integration for cost analysis
- Overmind Custom Signals submission
- Graduated severity scaling (-4 to +3) based on cost change percentage
- Support for both Overmind CLI and API submission methods
- Comprehensive cost analysis with top resource change detection
- Parallel execution with existing Terraform workflows
- Configurable thresholds and submission options
- Cross-platform support (Linux, macOS, Windows on GitHub Actions)
- Complete documentation and examples

### Features
- **Cost Analysis**: Real-time infrastructure cost impact analysis
- **Signal Submission**: Automatic submission to Overmind platform
- **Threshold Configuration**: Customizable percentage and absolute thresholds
- **Baseline Comparison**: Support for cost baseline comparisons
- **Rich Descriptions**: Detailed cost breakdowns with top contributing changes
- **Flexible Options**: Control over cost decrease signals and failure modes
- **Multi-Currency**: Support for USD, EUR, GBP and other currencies

### Supported Inputs
- `overmind-api-key` - Required Overmind API key
- `infracost-api-key` - Optional Infracost API key
- `terraform-plan-json` - Terraform plan JSON path (auto-detected)
- `threshold-percentage` - Percentage change threshold (default: 20%)
- `threshold-absolute` - Absolute dollar threshold (default: $500)
- `submit-on-decreases` - Submit signals for cost decreases (default: true)
- `fail-on-threshold` - Fail action on threshold breach (default: false)
- Various configuration options for customization

### Signal Value Scale
- `-4`: Critical increase (>100%)
- `-3`: High increase (50-100%)
- `-2`: Moderate increase (20-50%)
- `-1`: Minor increase (5-20%)
- `+1`: Minor reduction (5-20%)
- `+2`: Moderate reduction (20-50%)
- `+3`: Significant reduction (>50%)

### Dependencies
- Infracost v0.10.42+
- Overmind CLI (auto-installed)
- bc (for mathematical calculations)
- jq (for JSON processing)