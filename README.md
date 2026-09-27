# ServerBrain

**A self-hosted SRE agent that remembers every outage.**

Small startups run production on a single VPS with no SRE team, so every 2 a.m. incident gets debugged from scratch. ServerBrain watches your server, diagnoses failures from logs, recalls how similar incidents were fixed before, and proposes a fix you approve with one click in Discord. Every resolved incident becomes memory, so repeat outages get fixed faster.

> 🚧 Being built at the Invide AI Agent Buildathon (Bengaluru). Work in progress.

## How it works

```
detect → diagnose → recall → propose → approve → execute → verify → remember
```

1. **Detect**: monitors server health signals (CPU, memory, disk, services, containers, error rates).
2. **Diagnose**: analyzes logs to find the likely root cause.
3. **Recall**: retrieves similar past incidents and how they were resolved.
4. **Propose**: suggests a fix with its reasoning and risk level.
5. **Approve**: posts the proposal to a Discord channel with Approve / Reject buttons.
6. **Execute and verify**: runs the approved fix and confirms the system recovered.
7. **Remember**: writes the incident, root cause, and fix back into memory as a postmortem.

## Built on

- **ServerBrain / ZeroClaw ops agent**: currently monitoring a live production VPS
- **[Dialog](https://dialog-xi.vercel.app/)**: local-first AI log analysis
- **[FluctlightDB](https://github.com/voxmastery/FluctlightDB)**: Rust-core embedded memory engine for AI agents (`pip install fluctlightdb`)

## Roadmap (buildathon scope)

- [ ] Incident memory layer on FluctlightDB
- [ ] Log diagnosis pipeline via Dialog
- [ ] Discord approval flow for fixes (buttons)
- [ ] Incident timeline web UI
- [ ] Auto-generated postmortems

## Team

- Ganesh ([@voxmastery](https://github.com/voxmastery))

## License

MIT
