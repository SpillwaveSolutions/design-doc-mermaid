# Design Document with Mermaid Skill

A Claude Code skill for creating comprehensive, production-ready design documents with strategically placed Mermaid diagrams.

## Overview

This skill provides templates, references, and workflows for creating professional design documents that effectively combine written technical specifications with visual Mermaid diagrams. It supports five major design document types, each optimized for different documentation needs.

## Features

- **Five Production-Ready Templates** - Architecture, API, Feature, Database, and System Design
- **Integrated Mermaid Diagrams** - Strategic diagram placement for visual clarity
- **Comprehensive Syntax Guide** - Complete Mermaid diagram reference with examples
- **Workflow Documentation** - Step-by-step processes for creating and maintaining design docs
- **Code Sync Capabilities** - Patterns for keeping design docs aligned with code changes

## When to Use This Skill

Use this skill when you need to:

1. **Create design documents** - Generate comprehensive technical design documentation
2. **Update design docs** - Sync documentation with code changes
3. **Document architecture** - Create architecture decision records with visual diagrams
4. **Plan features** - Design new features with user flows and technical specifications
5. **Document APIs** - Create API specifications with request/response flows
6. **Design databases** - Document database schemas with ER diagrams
7. **System design** - Create complete system designs including scale and reliability

**Do NOT use this skill for:**
- Standalone diagrams without documentation (use mermaid-architect agent instead)
- Simple diagram-only requests (use mermaid-architect agent instead)

## Design Document Types

### 1. Architecture Design Document
**Template:** `assets/architecture-design-template.md`

Use for system-wide architectural decisions and patterns.

**Includes:**
- System context diagrams (C4)
- High-level architecture
- Data architecture
- Integration points
- Security architecture
- Deployment architecture
- Monitoring strategy
- Decision log (ADRs)

**Key Diagrams:** C4 Context, Architecture diagrams, Sequence diagrams, ER diagrams, State diagrams

### 2. API Design Document
**Template:** `assets/api-design-template.md`

Use for REST/GraphQL API specifications with visual flows.

**Includes:**
- API overview and base URLs
- Authentication flows
- Endpoint specifications
- Data models
- Request/response flows
- Error handling
- Rate limiting
- Webhooks

**Key Diagrams:** Sequence diagrams, ER diagrams, Flowcharts, State diagrams

### 3. Feature Design Document
**Template:** `assets/feature-design-template.md`

Use for individual feature specifications with UX and technical details.

**Includes:**
- Feature overview and user stories
- User journeys
- User flows
- Technical design
- Component interactions
- State machines
- Data models
- Deployment plan

**Key Diagrams:** User journey maps, Flowcharts, Class diagrams, Sequence diagrams, State diagrams, Gantt charts

### 4. Database Design Document
**Template:** `assets/database-design-template.md`

Use for database schema, data models, and query patterns.

**Includes:**
- Comprehensive ER diagrams
- Table specifications
- Index strategy
- Data access patterns
- Partitioning strategy
- Backup/recovery procedures
- Scaling strategy

**Key Diagrams:** ER diagrams, Architecture diagrams, Sequence diagrams, Flowcharts

### 5. System Design Document
**Template:** `assets/system-design-template.md`

Use for complete system design including scale, performance, and reliability.

**Includes:**
- System context
- High-level architecture
- Component design
- Data flows
- Database design
- Scaling strategy
- Caching layers
- Message queue architecture
- Security architecture
- Monitoring
- Disaster recovery

**Key Diagrams:** C4 Context, Multi-layer architecture, Sequence diagrams, ER diagrams, Flowcharts, Gantt charts

## Quick Start

### Creating a New Design Document

1. **Determine the document type** based on what you're documenting
2. **Copy the appropriate template** from the `assets/` directory
3. **Replace all placeholders** (e.g., `[System Name]`, `[Date]`, etc.)
4. **Customize Mermaid diagrams** to match your system
5. **Save to your project** in `docs/design/` directory

### Example Usage

```
User: "Create an architecture design doc for the contact manager system"

Process:
1. Use: assets/architecture-design-template.md
2. Create: docs/design/architecture-contact-manager-2025-01-15.md
3. Fill sections with contact manager details
4. Customize C4 diagrams for system context
5. Add component diagrams for architecture
6. Include ER diagrams for database
7. Add sequence diagrams for key flows
```

## File Structure

```
design-doc-mermaid/
├── README.md                             # This file
├── SKILL.md                              # Detailed skill documentation
├── assets/                               # Design document templates
│   ├── architecture-design-template.md
│   ├── api-design-template.md
│   ├── feature-design-template.md
│   ├── database-design-template.md
│   └── system-design-template.md
├── references/                           # Reference materials
│   └── mermaid-diagram-guide.md         # Mermaid syntax guide
└── scripts/                              # Utility scripts
```

## Mermaid Diagram Support

This skill includes comprehensive support for all major Mermaid diagram types:

- **Flowcharts** - Business logic and process flows
- **Sequence Diagrams** - API interactions and temporal flows
- **Class Diagrams** - Code structure and relationships
- **State Diagrams** - State transitions and workflows
- **ER Diagrams** - Database schemas and data models
- **User Journey** - User experience flows
- **Gantt Charts** - Project timelines and roadmaps
- **C4 Diagrams** - System context and architecture
- **Architecture Diagrams** - Infrastructure and deployment

See `references/mermaid-diagram-guide.md` for complete syntax reference and best practices.

## Usage Patterns

### Creating Design Documents

1. Choose the appropriate template
2. Copy to your project's `docs/design/` directory
3. Follow naming convention: `[type]-[name]-[YYYY-MM-DD].md`
4. Replace placeholders with actual content
5. Customize diagrams to match your system
6. Validate Mermaid syntax

### Updating Design Documents

1. Identify code changes using `git diff`
2. Map changes to design doc sections
3. Update affected text and diagrams
4. Add new diagrams for new components
5. Remove obsolete content
6. Update version and date

### Syncing with Code

1. Analyze recent commits
2. Update API specs if endpoints changed
3. Update ER diagrams if schema changed
4. Update architecture diagrams if components changed
5. Update sequence diagrams if flows changed

## Best Practices

1. **Start high-level, then add detail** - Begin with context, progress to specifics
2. **Keep diagrams focused** - One diagram = one concept, max 10-12 nodes
3. **Use consistent styling** - Define style classes and reuse
4. **Document decisions** - Include ADRs for key architectural choices
5. **Maintain living documents** - Update as code evolves
6. **Focus on critical paths** - Prioritize happy paths and key error scenarios

## Integration with Claude Code

This skill is designed for use with Claude Code. When activated, it provides:

- Template selection based on documentation needs
- Mermaid diagram syntax assistance
- Workflow guidance for creating and maintaining design docs
- Best practices for documentation structure

## Examples

### Diagram Type Selection

```
Need to show...              → Use this diagram
-------------------          → ------------------
System boundaries            → C4 Context
API interactions             → Sequence Diagram
Code structure               → Class Diagram
Database schema              → ER Diagram
State transitions            → State Diagram
Process flow                 → Flowchart
Timeline                     → Gantt Chart
User experience              → User Journey
Infrastructure               → Architecture Diagram
```

### Sample File Naming

```
docs/design/architecture-contact-manager-2025-01-15.md
docs/design/api-contacts-v1-2025-01-15.md
docs/design/feature-oauth-authentication-2025-01-15.md
docs/design/database-alloydb-schema-2025-01-15.md
docs/design/system-peak6-contactmanager-2025-01-15.md
```

## Related Skills and Agents

- **mermaid-architect agent** - For standalone Mermaid diagram generation
- **docs-sync-editor agent** - For syncing documentation with code changes
- **code-explainer agent** - For understanding code to document

## Resources

- [SKILL.md](SKILL.md) - Comprehensive skill documentation and workflows
- [Mermaid Diagram Guide](references/mermaid-diagram-guide.md) - Complete syntax reference
- [Mermaid Live Editor](https://mermaid.live) - Test and validate diagrams

## Contributing

When contributing to this skill:

1. Maintain template consistency
2. Validate all Mermaid syntax
3. Include examples for new features
4. Update both SKILL.md and README.md
5. Follow existing documentation patterns

## Version

**Version:** 1.0
**Last Updated:** 2025-01-02
**Status:** Active

## License

This skill is part of the Claude Code skills ecosystem.

---

**Need Help?**
- Read the detailed [SKILL.md](SKILL.md) for comprehensive usage instructions
- Refer to [mermaid-diagram-guide.md](references/mermaid-diagram-guide.md) for diagram syntax
- Check template files in `assets/` for examples
