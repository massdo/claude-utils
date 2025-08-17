# Claude Command: Notion Resume

This command helps you create comprehensive project summaries by discovering and analyzing project information from your Notion workspace using MCP.

## Usage

To resume a project, just type:
```
/notion-resume [-f] <project-name>
```

Examples:
```
/notion-resume laverie
/notion-resume -f laverie
```

### Options

- `-f`: Save the generated summary to `notion-resume-output.md` in the project root directory

## What This Command Does

1. **Engages specialized agent**: Uses @.claude/agents/agile-notion-expert.md for expert analysis of project structure and product vision
2. **Discovers project information** using Notion MCP search across your workspace and connected sources (Slack, Google Drive, Jira, etc.)
3. **Fetches relevant content** from discovered pages, databases, and documents
4. **Analyzes project structure** including goals, progress, team members, and key deliverables
5. **Evaluates product vision** with business objectives, target market, and strategic positioning
6. **Generates a comprehensive summary** in the same format as Claude Code's native `/resume` command
7. **Optionally saves output**: When using the `-f` flag, saves the generated summary to `notion-resume-output.md` in the project root

## Summary Format

The generated summary follows Claude Code's standard resume format with enhanced product insights:

### Project Overview
- **Name**: Project identifier
- **Description**: Brief project description
- **Status**: Current development phase
- **Timeline**: Key dates and milestones

### Product Vision
- **Business Objectives**: Core value proposition and strategic goals
- **Target Users**: Primary user segments and personas
- **Market Positioning**: Competitive landscape and differentiation
- **Success Metrics**: Key KPIs and measurable outcomes
- **Strategic Roadmap**: High-level milestones and vision evolution

### Technical Details
- **Technology Stack**: Languages, frameworks, and tools in use
- **Architecture**: High-level system design
- **Dependencies**: Key external libraries and services
- **Infrastructure**: Deployment and hosting information

### Agile Framework
- **Methodology**: Scrum, Kanban, or hybrid approach in use
- **Team Structure**: Roles and responsibilities (Product Owner, Scrum Master, etc.)
- **Sprint Information**: Current sprint status and velocity
- **Backlog Health**: Epic and story breakdown, prioritization status

### Team & Collaboration
- **Team Members**: Key contributors and their roles
- **Communication**: Meeting notes, decisions, and discussions
- **Documentation**: Links to key documents and resources
- **Workflow**: Development process and tool integrations

### Progress & Deliverables
- **Completed Features**: What has been built
- **Current Work**: Active development areas
- **Upcoming Tasks**: Planned work and priorities
- **Blockers**: Known issues or dependencies

### Resources
- **Repository**: Code location and branch information
- **Documentation**: Key design docs, specs, and guides
- **External Links**: Related tools, services, and references

## Search Strategy

The command searches for project information using multiple approaches:

1. **Direct project search**: Searches for pages/databases matching the project name
2. **Product documentation**: Finds PRDs, specifications, and strategic documents
3. **Sprint artifacts**: Locates backlog items, user stories, and sprint boards
4. **Team workspace search**: Locates team-specific pages and databases
5. **Connected sources**: Searches Slack conversations, Google Drive files, and Jira tickets
6. **Tag-based discovery**: Finds content tagged with the project name

## Agent Integration

This command leverages the **@.claude/agents/agile-notion-expert.md** agent which provides:

- **Agile Project Management Expertise**: Analysis of Scrum/Kanban processes, sprint health, and team dynamics
- **Advanced Notion Knowledge**: Understanding of complex database relationships and workflow automation
- **Product Strategy Insights**: Evaluation of business objectives, market positioning, and success metrics
- **Organizational Best Practices**: Assessment of documentation quality and team collaboration patterns

## Authorization

**Important**: This command will ask for explicit permission before accessing your Notion workspace, following the project's mandatory authorization requirements.

## Example Output

```
# Project Resume: laverie

## Overview
**Status**: Early Development  
**Type**: Web Application  
**Last Updated**: 2025-01-04

## Product Vision
**Business Objective**: Streamline laundromat operations and improve customer experience
**Target Users**: Laundromat owners and customers
**Key Success Metrics**: Customer satisfaction score, operational efficiency
**Market Position**: Premium self-service laundry management platform

## Technical Stack
- **Backend**: Node.js, Express
- **Database**: PostgreSQL
- **Frontend**: React, TypeScript
- **Infrastructure**: Docker, AWS

## Agile Framework
**Methodology**: Scrum (2-week sprints)
**Current Sprint**: Sprint 3 (Jan 1-14, 2025)
**Team Velocity**: 23 story points
**Backlog Health**: 45 stories, well-prioritized

## Current Progress
- [x] Initial project setup
- [x] Database schema design
- [ ] User authentication system
- [ ] Core business logic

## Team
- **Product Owner**: @mike.johnson
- **Scrum Master**: @sarah.kim
- **Lead Developer**: @john.doe
- **Designer**: @jane.smith

## Key Resources
- [Product Requirements](notion://...)
- [Technical Specification](notion://...)
- [Sprint Board](notion://...)
- [Design System](notion://...)
```

## Best Practices

- **Specific project names**: Use exact project identifiers for better search results
- **Regular updates**: Run this command periodically to stay current with project status
- **Team alignment**: Share generated summaries with team members for alignment
- **Documentation links**: Follow generated links to dive deeper into specific areas
- **Product focus**: Leverage the enhanced product vision analysis for strategic decisions

## Command Integration

This command works seamlessly with other Claude commands:
- Follow up with `/git-commit` to commit documentation updates
- Use insights to guide sprint planning and backlog refinement
- Reference product vision in feature development decisions

## Troubleshooting

- **No results found**: Check project name spelling and ensure it exists in your Notion workspace
- **Incomplete information**: The command only finds publicly accessible content in your workspace
- **Permission issues**: Ensure your Notion integration has appropriate access permissions
- **Agent not found**: Verify that @.claude/agents/agile-notion-expert.md exists in your project