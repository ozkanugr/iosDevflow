# Brainstorming Question Bank

Comprehensive question sets organized by project type and 5W1H category. Use these as the foundation for brainstorming sessions, adapting and expanding based on user responses.

---

## Universal Questions (All Project Types)

### WHO
1. Who is the primary user of this application?
2. What is their technical skill level?
3. What demographics define your target audience?
4. Who are secondary/indirect users?
5. Who are the project stakeholders (product owner, designers, QA)?
6. How large is the development team?
7. What experience level does the team have with the chosen technology stack?
8. Are there accessibility requirements for specific user groups?

### WHAT
1. Describe the core functionality in one sentence.
2. What are the top 3 problems this solves?
3. What existing apps/tools do users currently use for this?
4. What makes your solution different from existing alternatives?
5. What data types does the application handle?
6. What third-party services or APIs must it integrate with?
7. What are the non-negotiable features for v1.0?
8. What features are you explicitly deferring?
9. Does the app need to work offline?
10. What notification/communication features are needed?

### WHEN
1. What is the target MVP completion date?
2. What is the full v1.0 release target?
3. Are there external deadlines (events, regulations, contracts)?
4. What is the desired release cadence after v1.0?
5. Is there a beta/testing period planned?
6. Are there seasonal or market timing considerations?

### WHERE
1. Which platforms will this target?
2. What is the minimum version/environment requirement?
3. Where will this be distributed?
4. Where does the backend/API infrastructure live?
5. Where is user data stored? (On-device, cloud, custom server)
6. What geographic regions must be supported?
7. Are there data residency/sovereignty requirements?

### WHY
1. Why does this need to exist?
2. What business model supports this? (Free, Freemium, Paid, Subscription)
3. What KPIs define success for this project?
4. Why is now the right time to build this?
5. What happens if this project is not built?
6. What is the competitive advantage?

### HOW
1. What architecture pattern should be used?
2. What UI framework or approach?
3. How will the team handle code reviews?
4. How will CI/CD be configured?
5. How will secrets/credentials be managed?
6. How will performance be monitored?
7. How will error/crash reporting work?
8. What testing strategy? (Unit, Integration, UI, E2E)
9. How will localization be handled?
10. How will accessibility compliance be verified?

---

## Mobile App-Specific Questions

### User Experience
- What is the primary navigation pattern? (Tab bar, sidebar, stack)
- Are there onboarding/tutorial flows?
- What authentication method? (Social sign-in, email, biometric)
- What gestures and interactions are essential?
- Is haptic feedback important?
- What should the launch experience feel like?

### Platform Capabilities
- Does the app need background processing? What kind?
- Are push notifications required? What types?
- Does the app use the camera, microphone, or GPS?
- Are widgets or home screen features needed?
- Does the app need voice assistant integration?
- Are In-App Purchases or subscriptions required?

### Data & Networking
- What is the expected data volume per user?
- How frequently does data sync with a server?
- Is real-time data needed? (WebSockets, SSE)
- How is conflict resolution handled for synced data?
- What is the caching strategy?
- Are there specific API rate limits to consider?

---

## Library/Package-Specific Questions

### API Design
- What is the public API surface? (types, methods, protocols)
- What platforms/versions must be supported?
- Are there dependencies on other packages?
- How should the library handle errors?
- Is the API synchronous, asynchronous, or both?
- Should it support modern concurrency patterns?

### Distribution
- Will this be open source or private?
- What license applies?
- What versioning strategy? (SemVer)
- Is documentation generated?
- Are there sample apps or examples?

### Integration
- How do consumers integrate this? (Package manager, manual)
- What are the minimum dependency requirements?
- Does it need to be compatible with legacy code?
- Are there binary size constraints?

---

## Backend/Server-Specific Questions

### Infrastructure
- What hosting environment? (AWS, GCP, Azure, VPS, Docker)
- What database? (PostgreSQL, MySQL, MongoDB, SQLite)
- What is the expected request volume?
- What are the latency requirements?
- Is horizontal scaling needed?
- What queue/job processing is needed?

### API Design
- REST, GraphQL, or gRPC?
- What authentication/authorization model?
- What rate limiting applies?
- Is API versioning needed?
- What serialization format? (JSON, Protobuf, MessagePack)

### Operations
- How are logs collected and monitored?
- What alerting/on-call system is used?
- How are deployments performed?
- What is the rollback strategy?
- How are database migrations managed?

---

## Multi-Platform Questions

### Code Sharing
- What percentage of code should be shared across platforms?
- How will platform-specific features be handled?
- Will there be a shared package for core logic?
- How will UI differ between platforms?
- Are there platform-specific testing requirements?

### Consistency
- How consistent should the UX be across platforms?
- Should the app follow each platform's design guidelines?
- How will feature parity be managed?
- Is there a "primary" platform that leads development?

---

## CLI Tool Questions

### Command Structure
- What is the primary command structure? (subcommands, flags)
- What input formats are supported? (args, stdin, files)
- What output formats are needed? (text, JSON, table)
- Are interactive prompts required?
- Should it support configuration files?

### Integration
- How will users install the tool?
- What shell environments must be supported?
- Does it need to integrate with other CLI tools?
- What environment variables are used?
- Are there autocomplete requirements?

---

## Follow-Up Question Patterns

### When answers are vague
- "Can you give me a specific example of what that would look like?"
- "If you had to choose just one, which would it be?"
- "What does success look like for that feature specifically?"

### When answers reveal complexity
- "That sounds like it could be broken into several features. Shall we decompose it?"
- "What is the simplest version of that feature that would still be valuable?"
- "Are there dependencies between those requirements?"

### When answers conflict
- "Earlier you mentioned {X}, but this seems to conflict with {Y}. How should we reconcile?"
- "Given the timeline you mentioned, is this feature realistic for v1.0?"
- "This requirement might impact {other requirement}. How should we prioritize?"

---

## Depth Indicators

Use these to gauge when to move on:

| Indicator | Action |
|-----------|--------|
| User gives detailed, specific answers | Move to next question |
| User hesitates or gives vague answer | Probe deeper with follow-ups |
| User explicitly says "I don't know" | Offer 2-4 concrete options |
| User says "not applicable" | Acknowledge and move on |
| User contradicts earlier answer | Clarify and reconcile |
