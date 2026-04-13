# gate22-poc

Replica of aipotheosis-labs/gate22's CI workflow.

Demonstrates fork checkout + docker compose secret exposure:
- `pull_request_target` triggers on any fork PR
- Environment gate `CICD_FOR_FORKED_REPO` only has branch_policy (no required_reviewers)
- `test` job checks out fork code and runs `docker compose` with OpenAI API keys in env
- Attacker replaces `compose.ci.yml` to exfiltrate secrets

Used for authorized security research only.
