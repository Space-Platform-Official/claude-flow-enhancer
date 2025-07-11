---
allowed-tools: all
description: Orchestrate multiple sub-agents to complete complex tasks and plans in parallel
---

# Orchestrate Command

This command creates and manages multiple sub-agents to execute tasks and plans generated by Claude Code in parallel.

## Task Analysis and Decomposition

$ARGUMENTS

## Orchestration Strategy

### 1. Task Breakdown
First, I'll analyze the provided tasks/plans and decompose them into independent work units that can be executed in parallel:

- Identify dependencies between tasks
- Group related tasks that share context
- Determine optimal parallelization strategy
- Estimate complexity and resource requirements for each sub-task

### 2. Agent Spawning Pattern

Based on the task analysis, I'll spawn specialized agents using these patterns:

#### Pattern A: File-Based Parallelization
When tasks involve multiple files, spawn one agent per file or file group:
```
Agent 1: Handle authentication module (auth.ts, auth.test.ts)
Agent 2: Handle database layer (db/*.ts)
Agent 3: Handle API endpoints (api/*.ts)
```

#### Pattern B: Feature-Based Distribution
For feature implementation, spawn agents for different aspects:
```
Agent 1: Research existing patterns and dependencies
Agent 2: Implement core functionality
Agent 3: Write comprehensive tests
Agent 4: Update documentation and types
```

#### Pattern C: Layer-Based Separation
For full-stack tasks, spawn agents per layer:
```
Agent 1: Frontend components and UI
Agent 2: Backend API and business logic
Agent 3: Database schema and migrations
Agent 4: Integration and E2E tests
```

### 3. Agent Instructions Template

Each spawned agent will receive:

1. **Context**: Relevant codebase information and dependencies
2. **Specific Task**: Clear, bounded work scope
3. **Success Criteria**: Measurable completion requirements
4. **Coordination Notes**: How their work relates to other agents

### 4. Execution Workflow

#### Phase 1: Reconnaissance (Parallel)
Spawn agents to explore different areas of the codebase:
- Agent A: Map existing architecture and patterns
- Agent B: Identify potential integration points
- Agent C: Analyze test coverage and quality standards

#### Phase 2: Implementation (Parallel)
Based on reconnaissance, spawn implementation agents:
- Each agent handles an independent module/feature
- Agents work within clearly defined boundaries
- No overlapping file modifications between agents

#### Phase 3: Integration (Sequential)
After parallel work completes:
- Review all agent outputs
- Resolve any conflicts or inconsistencies
- Run comprehensive tests across all changes
- Ensure cohesive integration

### 5. Task Tracking and Monitoring

I'll maintain a central tracking system:

```
Task Status Board:
├── Agent 1: Authentication Module [IN PROGRESS]
│   ├── Subtask 1.1: JWT implementation ✓
│   ├── Subtask 1.2: Session management ⧗
│   └── Subtask 1.3: Tests pending
├── Agent 2: Database Layer [COMPLETED]
│   ├── Subtask 2.1: Schema design ✓
│   ├── Subtask 2.2: Migration scripts ✓
│   └── Subtask 2.3: Query optimization ✓
└── Agent 3: API Endpoints [IN PROGRESS]
    ├── Subtask 3.1: Route handlers ✓
    ├── Subtask 3.2: Validation middleware ⧗
    └── Subtask 3.3: OpenAPI spec pending
```

### 6. Result Aggregation

After all agents complete their tasks:

1. **Collect Outputs**: Gather all code changes, test results, and documentation
2. **Verify Integrity**: Ensure no conflicts between agent outputs
3. **Run Integration Tests**: Verify the combined work functions correctly
4. **Generate Summary**: Create comprehensive report of all completed work

### 7. Quality Assurance

Each agent must:
- Follow existing code patterns and conventions
- Write tests for all new functionality
- Ensure zero linting errors or warnings
- Document complex logic and API changes
- Verify backward compatibility

### 8. Parallel Execution Rules

To maximize efficiency while avoiding conflicts:

1. **File Locking**: No two agents modify the same file
2. **Clear Boundaries**: Each agent has exclusive ownership of their assigned modules
3. **Shared Resources**: Read-only access to common utilities and types
4. **Communication**: Agents document interface contracts for integration points

## Example Orchestration

For a task like "Implement user authentication system with OAuth support":

```
Orchestration Plan:

PARALLEL PHASE 1 - Research (3 agents):
├── Agent 1: Research existing auth patterns in codebase
├── Agent 2: Analyze OAuth provider requirements
└── Agent 3: Study current user model and database schema

PARALLEL PHASE 2 - Implementation (4 agents):
├── Agent 1: Implement OAuth provider integrations
├── Agent 2: Create authentication middleware and guards
├── Agent 3: Build user session management
└── Agent 4: Develop authentication UI components

PARALLEL PHASE 3 - Testing (2 agents):
├── Agent 1: Write unit and integration tests
└── Agent 2: Create E2E authentication flows

SEQUENTIAL PHASE 4 - Integration:
└── Main orchestrator: Integrate all components and verify
```

## Command Completion

Upon completion, I'll provide:
1. Summary of all agent activities and outcomes
2. List of all modified files with change descriptions
3. Test coverage report
4. Any unresolved issues or recommendations
5. Next steps for deployment or further development

Remember: Effective orchestration means maximizing parallel work while maintaining code quality and consistency across all agents.