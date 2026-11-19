# Output schema (human-readable or JSON)
scope: {mode, urls, date, evidence_access, limitations}
policy: [{rule_id, source_url, status, observed_evidence, action}]
editorial: {weighted_score, dimensions:[{name, weight, score, rationale}], release_decision}
claims: [{claim_id, claim, evidence, verification, action}]
arguments: [{claim_id, mechanism, alternatives, verdict, required_evidence}]
issues: [{location, severity, category, observation, recommendation, validation}]
economics: {available_data, conclusions, uncertainty, experiments}
priority_plan: [{priority, task, owner_optional, validation, dependency}]
Never return a fabricated 'approval likelihood' field.
