# PPT Production Handoff

## Human-readable package

Include:

1. Assignment and success criterion
2. Audience influence map
3. One-page executive summary
4. Message map and solution closure map
5. Chapter framework and page budget
6. Management view
7. Detailed slide briefs
8. Speaker outlines and transitions
9. Key question/objection bank
10. Evidence and asset list
11. Quality and permission summary
12. Project-memory draft

## Structured package

Use YAML or JSON. Keep deck-level and slide-level records synchronized with the human-readable version. Use evidence objects rather than untyped strings so the production skill can preserve provenance and readiness.

```yaml
deck:
  title: ""
  audience: []
  meeting_context: ""
  success_criterion: ""
  core_claim: ""
  requested_action: ""
  duration_minutes: 0
  visual_constraints: []
slides:
  - number: 1
    title: ""
    purpose: ""
    primary_audience: []
    cognitive_change: ""
    key_message: ""
    supporting_points: []
    evidence:
      - claim: ""
        source: ""
        source_date: ""
        source_type: "fact"
        confidence: "high"
        evidence_grade: "A"
        permission: "approved"
        status: "verified"
    layout: ""
    visual_type: ""
    visual_focus: ""
    assets: []
    speaker_outline: []
    transition: ""
    permissions: ""
    readiness_status: "CONFIRM"
```

Allowed evidence values:

- `source_type`: `fact`, `executive_statement`, `opinion`, `inference`, or `assumption`
- `confidence`: `high`, `medium`, or `low`
- `evidence_grade`: `A`, `B`, `C`, or `D`
- `permission`: `approved`, `internal-only`, `restricted`, or `confirm`
- `status`: `verified`, `unverified`, `conflicting`, or `missing`

Do not default a slide to `READY`. Assign readiness only after checking content, evidence, assets, and permissions. Use the statuses defined in [slide-brief-schema.md](slide-brief-schema.md).

## Project-memory draft

Summarize current stage, confirmed facts and terminology, stakeholder changes, current content master, audience variants, decisions, evidence gaps, source index, and recommended next reading. Do not persist it without explicit permission.

## Completion prompt

Only when the final gate passes, end with exactly:

> 终稿已经形成，你可以直接调用PPT生成Skill进行输出。

