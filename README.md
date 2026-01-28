# Integration SNOW L1/L2 Support Prompts

AI-powered prompt repository for ServiceNow L1/L2 Support teams handling EDI integration failures on Seeburger BIC/BIS and OpenText AMPS platforms.

## 🎯 Purpose

This repository provides standardized prompts for AI-assisted analysis of:
- **Seeburger BIC** (Business Integration Center) mapping errors
- **Seeburger BIS** (Business Integration Suite) process errors
- **OpenText AMPS** translation failures
- General EDI troubleshooting and partner communication

## 🏗️ Repository Structure

```
integration-snow-L1L2-prompts/
├── README.md
├── LICENSE
├── CHANGELOG.md
├── config/
│   ├── prompt-config.json          # Configuration for prompt loading
│   └── error-codes.json            # Error code mappings
├── seeburger/
│   ├── README.md
│   ├── bic/
│   │   ├── inbound/
│   │   │   ├── system-prompt.md
│   │   │   ├── bicmapping-errors.md
│   │   │   ├── syntax-errors.md
│   │   │   └── validation-errors.md
│   │   └── outbound/
│   │       ├── system-prompt.md
│   │       ├── mandatory-field-errors.md
│   │       └── transformation-errors.md
│   └── bis/
│       ├── inbound/
│       │   └── system-prompt.md
│       ├── outbound/
│       │   ├── system-prompt.md
│       │   ├── scp-process-errors.md
│       │   └── table-lookup-errors.md
│       └── common/
│           └── http-forwarding-errors.md
├── opentext/
│   ├── README.md
│   └── amps/
│       ├── system-prompt.md
│       ├── translation-errors.md
│       └── lookup-failures.md
├── classification/
│   ├── README.md
│   ├── system-prompt.md
│   ├── partner-data-issue.md
│   ├── map-configuration-issue.md
│   └── system-issue.md
├── email-templates/
│   ├── README.md
│   ├── partner-notification.md
│   ├── internal-escalation.md
│   └── cr-recommendation.md
├── analysis/
│   ├── README.md
│   ├── root-cause-analysis.md
│   ├── error-summary.md
│   └── technical-to-business.md
└── workflows/
    ├── README.md
    ├── l1-triage-workflow.md
    ├── l2-analysis-workflow.md
    └── end-to-end-resolution.md
```

## 📚 Error Categories Covered

### Seeburger BIC Mapping Errors

| Error Code | Description | Example |
|------------|-------------|----------|
| 2087 | Field value too large | `Value of incoming field is too large. Segment:'TDT', Field:'3128', MaxLength:'35'` |
| 3031 | Mandatory field not filled | `Mandatory Field 'UNB.UNH.SG10.NAD:C059.3042[1]' not filled` |
| 910 | Table entry missing | `SCAC_DANONE_SAP entry for missing in DANONE_PARTNER_TABLE` |
| (not set) | Fatal Java exception | `IndexOutOfBoundsException: Index -1 out of bounds` |

### Seeburger BIS Process Errors

| Error Type | Description |
|------------|-------------|
| SCP HTTP Errors | 500 status codes from SCP APIs |
| Conditional Stop | Process interrupted due to condition evaluation |
| Postprocessing Errors | Failures in post-processing activities |

## 🚀 Quick Start

### 1. Clone the Repository
```bash
git clone https://github.com/Ashok-Kumar-Maersk/integration-snow-L1L2-prompts.git
```

### 2. Configure Your Application
```json
{
    "prompt_repository": {
        "type": "github",
        "url": "https://github.com/Ashok-Kumar-Maersk/integration-snow-L1L2-prompts",
        "branch": "main"
    }
}
```

### 3. Use Prompts
The prompts are designed to work with:
- EDI Failure Analyzer application
- GitHub Copilot
- Azure OpenAI / ChatGPT

## 📋 Use Cases

Based on ServiceNow Support requirements:

### Use Case 1: BIC Mapping Error - Mandatory Field
**Scenario**: `BICMapping ERROR(3031): Mandatory Field not filled`

### Use Case 2: BIC Mapping Error - Field Too Large
**Scenario**: `BICMapping ERROR(2087): Value of incoming field is too large`

### Use Case 3: SCP Process Error
**Scenario**: `CAUGHT HANDLED EXCEPTION` with HTTP 500 error

### Use Case 4: Table Lookup Missing
**Scenario**: `FATAL 910 entry missing in TABLE`

### Use Case 5: Java Exception in Mapping
**Scenario**: `Fatal exception in user mapping java.lang.IndexOutOfBoundsException`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Follow the prompt template format
4. Submit a pull request

## 📄 License

MIT License - See [LICENSE](LICENSE) for details.
