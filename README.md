# prelegal

A legal document template engine: a curated dataset of standard legal agreement templates that the system can modify for the user.

## What's in this repo

| Path | Purpose |
| --- | --- |
| `templates/` | Legal agreement templates in Markdown |
| `templates/LICENSE.txt` | Notice that everything under `templates/` is licensed CC BY 4.0 |
| `catalog.json` | Index of every template: `name`, `description`, and `filename` |

## Templates

The catalog currently includes 12 templates from [Common Paper](https://github.com/CommonPaper):

- **AI Addendum** — AI-specific terms bolted onto an existing agreement
- **Business Associate Agreement (BAA)**
- **Cloud Service Agreement (CSA)**
- **Data Processing Agreement (DPA)**
- **Design Partner Agreement**
- **Mutual Non-Disclosure Agreement** (+ its **Cover Page** companion)
- **Partnership Agreement**
- **Pilot Agreement**
- **Professional Services Agreement (PSA)**
- **Service Level Agreement (SLA)**
- **Software License Agreement**

Each directory entry in `catalog.json` looks like:

```json
{
  "name": "Cloud Service Agreement (CSA)",
  "description": "Common Paper standard Cloud Service Agreement: Key Terms, Standard Terms, Order Forms, and SOW structure for SaaS subscriptions.",
  "filename": "CSA.md"
}
```

## Licensing

The templates come from [Common Paper's GitHub](https://github.com/CommonPaper), where they are released under the [Creative Commons Attribution 4.0 International license (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). That means:

- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material for any purpose, including commercial use

As long as you give appropriate credit and indicate any changes. See `templates/LICENSE.txt` for the full notice.

## Using the templates in your product

The system's goal (tracked in Jira task `PL-2`) is to allow automated, programmatic modification of these templates for users. A typical workflow looks like:

1. Read `catalog.json` to find the right template by name or description.
2. Load the template from `templates/<filename>`.
3. Modify it programmatically — cover-page fields, key terms, clauses, or jurisdiction-specific edits.
4. Emit a customized document.

## Contributing

Template updates flow from upstream Common Paper releases. When adding a new template:

1. Drop the markdown file into `templates/`.
2. Add a matching entry to `catalog.json`.
3. Confirm the license attribution in `templates/LICENSE.txt` still covers it.
