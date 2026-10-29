VU PREP AI
## FINAL Master Product Requirements and Engineering Plan — Claude Handoff

**Revision:** 2026-10-29 | **Status:** Proposed final specification for developer approval. No implementation authorized.

**Project:** VU Prep AI  
**Product Type:** AI-powered exam preparation SaaS  
**Initial Audience:** Virtual University of Pakistan students  
**Project Status:** Pre-development; no application implementation authorized  
**Primary Framework:** Next.js with TypeScript  
**Development Methodology:** Approval-based, incremental development with mandatory pre-AI testing gates

---

# 1. PRODUCT VISION

Build an intelligent, reliable, accessible and scalable AI-powered exam preparation platform for Virtual University of Pakistan students.

The platform should transform lengthy university handout PDFs into interactive, personalized and exam-focused learning experiences.

Students should be able to upload a PDF and automatically receive structured preparation materials without writing prompts.

The platform must support both direct handout-based examination questions and questions that test the same concepts using different wording or scenarios.

The system must prioritize educational accuracy, source traceability, practical usability, student privacy and efficient AI usage.

Our long-term objective is to validate the product with real VU students and potentially develop it into a sustainable EdTech startup.

# 2. CORE PRODUCT PRINCIPLES

1. PDF-first and prompt-free onboarding.
2. Handout-grounded learning.
3. Source-referenced AI-generated content.
4. Accurate and comprehensive content processing.
5. Simple and intuitive student experience.
6. Interactive, context-aware AI tutoring.
7. Personalized exam preparation.
8. Efficient processing of lengthy PDFs.
9. Transparent AI limitations.
10. Secure handling of student information.
11. Cost-conscious and scalable architecture.
12. Production-quality engineering practices.

The application must not claim to predict actual examination questions or guarantee examination results.

# 3. TARGET USERS

Initially, the platform will serve Virtual University of Pakistan students.

Typical users include:

- Students preparing for midterm examinations.
- Students preparing for final examinations.
- Students with limited preparation time.
- Students struggling with lengthy handouts.
- Students who understand concepts but miss specific handout facts.
- Students who need explanations in Roman Urdu.
- Students who want structured English revision notes.
- Students who need repeated MCQ practice.

The initial product should remain focused on VU rather than attempting to support every educational institution.

# 4. COMPLETE STUDENT JOURNEY

## 4.1 First Visit

A student visits the platform.

The landing page clearly explains the product's purpose and benefits.

The student can begin by selecting a PDF.

Authentication requirements must be designed to minimize onboarding friction while protecting processing resources and preventing abuse.

## 4.2 PDF Upload

The student uploads a university handout PDF. Initial product policy: one new handout per authenticated student per Pakistan-calendar day, up to 500 pages and 30 MB, subject to validated infrastructure capacity. The user can re-open existing documents without consuming another allowance. A failed upload or failed processing job must not permanently consume the allowance. Application allowance is independent of the provider quota reset timezone. Scanned PDFs are not promised in MVP; flag them clearly.

The platform:

- Validates file type and size.
- Performs appropriate file security checks.
- Stores the file securely.
- Creates a processing job.
- Displays processing progress.
- Handles errors and failed processing.
- Avoids duplicate processing where practical.

## 4.3 Automatic Analysis

The platform automatically (without invoking Gemini unless a separately approved step requires it):

- Extracts PDF text.
- Detects lecture boundaries where possible.
- Identifies topics and subtopics.
- Extracts definitions.
- Identifies technical terminology.
- Extracts important facts.
- Identifies comparisons and relationships.
- Detects formulas, tables and relevant examples.
- Preserves source page references.
- Records extraction limitations.

The system must handle PDFs with different layouts.

Scanned PDFs and OCR support should be evaluated separately based on complexity and cost.

## 4.4 Preparation Dashboard

After deterministic extraction and lecture-structure processing, the student receives a subject-specific dashboard. Generative AI content is NOT required before showing the dashboard (Option B). Generate explanations, revision, MCQs and detailed material on demand, cache verified results, and show distinct statuses for extraction, structure, and AI generation.

The dashboard should provide:

- Lecture navigation.
- Topic navigation.
- Learn Topics.
- Quick Revision.
- Complete Exam Coverage.
- Important Definitions.
- Important Facts.
- MCQ Practice.
- AI Tutor.
- Mock Exams.
- Exam Rescue Mode.
- Preparation Progress.

Features not yet implemented must not appear functional.

# 5. AI LEARNING SYSTEM

## 5.1 Interactive Topic Explanations

Students can select a topic and receive a clear explanation in Roman Urdu.

Requirements:

- Roman Urdu explanations by default.
- English technical terminology.
- Simple examples.
- Step-by-step explanations for complex concepts.
- Clear distinctions between related concepts.
- Handout-grounded information.
- Relevant page references.
- Adaptation to student questions.

## 5.2 Interactive AI Tutor

Students must be able to ask questions while studying.

The AI tutor should:

- Understand the currently selected subject.
- Understand the current lecture and topic.
- Use relevant uploaded handout content.
- Support multi-turn conversations.
- Maintain appropriate conversation context.
- Answer follow-up questions.
- Explain concepts using alternative examples.
- Distinguish handout information from supplementary explanations.
- Admit when information cannot be verified.
- Avoid fabricated source references.

The tutor should not unnecessarily send the entire PDF to the AI model for every question.

Investigate retrieval-based context selection and efficient conversation memory.

## 5.3 Quick Revision

Generate concise notes in basic English.

Notes should contain:

- Essential definitions.
- Key concepts.
- Important facts.
- Technical terminology.
- Short comparisons.
- Formulas where applicable.
- Critical points worth remembering.

Quick Revision must be concise without misleading students about omitted content.

## 5.4 Complete Exam Coverage

Provide detailed lecture-wise preparation material.

The system should aim to preserve and cover examinable information, including:

- Definitions.
- Factual statements.
- Conceptual relationships.
- Comparisons.
- Technical terminology.
- Formulas.
- Relevant examples.
- Important exceptions.
- Other testable details.

Complete Coverage does not mean a guarantee that every possible exam question has been covered.

The platform must distinguish successfully processed content from unprocessed or uncertain content.

# 6. MCQ GENERATION ENGINE

Generate MCQs in English based primarily on uploaded handouts.

Supported question categories:

1. Direct handout-based MCQs.
2. Definition-based MCQs.
3. Fact-based MCQs.
4. Conceptual MCQs.
5. Comparison-based MCQs.
6. Scenario-based MCQs.
7. Conceptually reworded MCQs.
8. Tricky but fair MCQs.

Every MCQ should include:

- Question.
- Answer options.
- Correct answer.
- Roman Urdu explanation.
- Relevant lecture and topic.
- Source reference.
- Question category.
- Difficulty level where appropriate.

The system should implement quality checks to reduce:

- Incorrect answers.
- Ambiguous questions.
- Duplicate questions.
- Unsupported claims.
- Weak distractors.
- Incorrect source references.

The system must not present AI-generated MCQs as official VU examination questions.

# 7. INTERACTIVE QUIZ SYSTEM

Students should be able to:

- Attempt topic-wise quizzes.
- Attempt lecture-wise quizzes.
- Attempt mixed-topic quizzes.
- Submit answers.
- Review incorrect answers.
- Read Roman Urdu explanations.
- Revisit relevant handout sections.
- Retry weak topics.
- View practice history.

Answers must be evaluated using reliable structured question data.

Quiz scoring should not depend on asking an LLM to judge every ordinary multiple-choice submission.

# 8. STUDENT PROGRESS AND PERSONALIZATION

Track:

- Topics studied.
- Lectures practiced.
- Questions attempted.
- Correct and incorrect answers.
- Practice accuracy.
- Repeated mistakes.
- Weak topics.
- Revision activity.
- Mock exam results.

Use this information to recommend useful next learning activities.

Clearly distinguish:

- Document processing coverage.
- Study completion.
- Practice accuracy.
- Estimated preparation progress.

Do not represent practice accuracy as a guaranteed examination score.

# 9. MOCK EXAM SYSTEM

Students should be able to take timed practice examinations.

Features:

- Configurable question counts.
- Timed attempts.
- Mixed-topic questions.
- Question navigation.
- Automatic scoring.
- Result review.
- Incorrect-answer explanations.
- Performance breakdown.

Any VU-specific examination settings must be verified before being implemented as official or default examination patterns.

# 10. EXAM RESCUE MODE

Design a preparation mode for students with limited time.

Example:

A student has six hours before an examination.

The system should generate a practical study plan based on:

- Available preparation time.
- Successfully analyzed handout content.
- Topic coverage.
- Student practice performance.
- Topic complexity.
- Reliable historical examination information, if legally available.

The system should prioritize learning activities without falsely guaranteeing that lower-priority material will not appear in an examination.

# 11. HANDOUT COVERAGE AND SOURCE TRACEABILITY

This is a critical product requirement.

The system should maintain traceable relationships between:

- Uploaded PDF.
- Document pages.
- Extracted text.
- Lectures.
- Topics.
- Important facts.
- Generated notes.
- Generated questions.

Source references must be verified against stored source material.

The application should communicate:

- Successfully processed pages.
- Unprocessed pages.
- Extraction failures.
- Missing or uncertain content.
- Processing status.

Avoid fabricated page numbers or unsupported claims of complete examination coverage.

# 12. PROPOSED TECHNOLOGY STACK

## Frontend

- Next.js App Router
- TypeScript
- Tailwind CSS
- Accessible reusable UI components

## Authentication and Database

- Supabase Auth
- PostgreSQL

## Document Storage

- AWS S3

## Document Processing

- Python worker using PyMuPDF as the initial candidate; benchmark against representative VU handouts before committing.
- Local extraction and page mapping before any Gemini request.
- Deterministic lecture detection first; low-confidence fallback requires approval before AI use.
- Student correction flow for uncertain lecture boundaries.

## AI

- An appropriate LLM API
- Structured outputs where supported
- Retrieval-based context selection where beneficial
- Model and provider selection based on quality, latency, reliability and cost

## Background Processing

- A PostgreSQL-backed durable queue is the default MVP candidate; validate reliability and worker hosting before approval.
- Durable job processing.
- Retry handling.
- Idempotent processing.
- Observable job status.

Evaluate whether a separate queue and worker infrastructure is necessary for the MVP.

## Deployment

- Docker
- Appropriate cloud hosting
- Secure environment configuration
- CI/CD
- Application monitoring

These technologies are proposed, not mandatory architectural decisions.

Claude must evaluate their suitability and recommend changes when justified.

Avoid unnecessary microservices and Kubernetes infrastructure during the initial MVP.

# 13. PROPOSED APPLICATION MODULES

The architecture should separate the following responsibilities:

1. Authentication and user management.
2. PDF upload and document management.
3. Document extraction.
4. Lecture and topic identification.
5. AI content generation.
6. Source verification.
7. AI tutoring.
8. MCQ generation and validation.
9. Quiz attempts and scoring.
10. Student progress tracking.
11. Mock examinations.
12. Exam Rescue planning.
13. Background job management.
14. Usage limits and cost tracking.
15. Monitoring and error handling.

Claude should propose appropriate boundaries without introducing unnecessary complexity.

# 14. DATABASE DESIGN

Claude should propose a relational data model covering:

- Users and profiles.
- Documents.
- Processing jobs.
- Extracted pages.
- Lectures.
- Topics.
- Source references.
- Generated notes.
- Generated questions.
- Question options.
- Quiz attempts.
- Student answers.
- AI tutor conversations.
- Tutor messages.
- Learning progress.
- Mock exams.
- Usage records.

Requirements:

- Appropriate foreign keys.
- Suitable indexes.
- Data integrity.
- Row-level security where applicable.
- User data isolation.
- Document ownership.
- Deletion and retention handling.
- Schema migrations.

Do not create database tables before the proposed schema has been reviewed and approved.

# 15. AI RELIABILITY REQUIREMENTS

The system should use an evidence-first approach.

Consider a processing pipeline such as:

PDF → Extraction → Structure Detection → Topic Mapping → Fact Extraction → Content Generation → Verification → Storage

Important requirements:

- Source-grounded answers.
- Structured AI outputs.
- Validation of generated content.
- Retry and failure handling.
- Detection of unsupported claims.
- Appropriate confidence or uncertainty reporting.
- Duplicate question detection.
- Reusable generated content.
- Versioning or invalidation when source documents change.

The architecture should allow evaluation against manually reviewed handout content.

Do not assume that an LLM can guarantee 100% coverage or accuracy.

# 16. PERFORMANCE AND COST MANAGEMENT

The application should be designed with sustainable operating costs in mind.

Investigate:

- PDF content caching.
- Document fingerprints.
- Reusing previously generated material.
- Processing large PDFs in manageable sections.
- Batching AI requests where appropriate.
- Efficient context retrieval.
- Background processing.
- Rate limits.
- Per-user usage limits.
- Token usage monitoring.
- AI request cost tracking.
- Storage lifecycle management.
- Failed job recovery.

Avoid repeatedly processing the same document without a valid reason.

# 17. SECURITY, PRIVACY AND COPYRIGHT

Security requirements include:

- Server-side file validation.
- File size limits.
- Appropriate malware scanning or isolation strategy.
- Private document storage.
- Secure signed access where appropriate.
- Authentication and authorization.
- User-level data isolation.
- Secure API endpoints.
- Server-side secret management.
- Rate limiting.
- Abuse prevention.
- Safe processing of untrusted PDF content.
- Protection against prompt injection from uploaded documents.
- Secure error handling.
- Data retention and deletion policies.

University handouts may contain copyrighted material.

The application must not publicly redistribute uploaded university documents without appropriate permission.

Before public launch, review relevant copyright, privacy and institutional requirements.

# 18. UI/UX REQUIREMENTS

Design a polished, professional educational SaaS experience.

Priorities:

- Modern and minimal interface.
- Clear typography.
- Accessible colors and controls.
- Responsive layouts.
- Simple navigation.
- Clear processing states.
- Useful loading indicators.
- Helpful error messages.
- Accessible quiz interactions.
- Distraction-free reading.
- Easy switching between explanations and practice.

Avoid unnecessary animations and visual complexity.

The design should support students studying under time pressure.

# 19. DEVELOPMENT PHASES

## Phase 0 — Architecture and Planning

Deliverables:

- Requirements review.
- Architecture proposal.
- Technology evaluation.
- Data model proposal.
- AI processing strategy.
- Security strategy.
- Development roadmap.
- MVP scope.
- Testing strategy.
- Risk assessment.

No application implementation is permitted before approval.

## Phase 1 — Next.js Foundation

- Initialize project.
- Configure TypeScript.
- Configure styling.
- Establish project structure.
- Configure development tooling.
- Establish code quality standards.

## Phase 2 — UI/UX Foundation

- Design system.
- Landing page.
- Navigation.
- Dashboard layout.
- Upload interface.
- Reusable components.
- Responsive behavior.

## Phase 3 — Authentication and Database

- Supabase integration.
- Authentication.
- Protected routes.
- User profiles.
- Database schema.
- Row-level security.

## Phase 4 — PDF Upload and Storage

- PDF validation.
- Secure storage.
- Document records.
- Upload progress.
- Document management.
- Processing status.

## Phase 5 — PDF Processing Engine

- Text extraction.
- Page mapping.
- Lecture detection.
- Topic identification.
- Structured content storage.
- Extraction validation.
- Error handling.

## Phase 6 — AI Learning Material

- AI provider integration.
- Topic explanations.
- Quick Revision.
- Complete Coverage.
- Definitions and facts.
- Source references.
- Content validation.

## Phase 7 — Interactive AI Tutor

- Topic-aware chat.
- Roman Urdu responses.
- Conversation persistence.
- Handout-grounded retrieval.
- Source references.
- Follow-up questions.
- Cost controls.

## Phase 8 — MCQ and Quiz Engine

- MCQ generation.
- Question validation.
- Question storage.
- Quiz interfaces.
- Answer submission.
- Scoring.
- Explanation display.

## Phase 9 — Student Analytics

- Practice history.
- Topic progress.
- Weak-topic detection.
- Performance dashboard.
- Personalized recommendations.

## Phase 10 — Mock Exams and Exam Rescue

- Timed mock exams.
- Results and review.
- Exam Rescue plans.
- Time-based preparation.
- Personalized revision recommendations.

## Phase 11 — Production Hardening

- Automated tests.
- Integration tests.
- AI quality evaluations.
- Security review.
- Accessibility testing.
- Performance optimization.
- Cost optimization.
- Monitoring.
- Failure recovery.

## Phase 12 — Deployment and Beta Testing

- Production configuration.
- Docker deployment.
- CI/CD.
- Monitoring.
- Limited VU student beta.
- Feedback collection.
- Product improvements.

# 20. TESTING STRATEGY

The project must include appropriate tests throughout development.

Testing categories:

- Unit tests.
- Component tests.
- API integration tests.
- Authentication and authorization tests.
- PDF processing tests.
- AI output validation.
- Source reference verification.
- Quiz scoring tests.
- End-to-end tests.
- Accessibility tests.
- Performance tests.
- Security tests.

Create a small manually reviewed evaluation dataset from permitted VU handout material.

Measure:

- Extraction completeness.
- Lecture detection accuracy.
- Topic identification quality.
- Important fact coverage.
- MCQ correctness.
- Source citation accuracy.
- AI tutor grounding.
- Processing time.
- Processing cost.

# 21. MVP DEFINITION

The first genuinely usable MVP should allow a student to:

1. Access the application.
2. Upload a supported PDF.
3. Wait for automatic processing.
4. Navigate detected lectures and topics.
5. Read Roman Urdu topic explanations.
6. Ask follow-up questions.
7. Read basic English Quick Revision notes.
8. Access detailed preparation material.
9. Practice English MCQs.
10. Review answers and explanations.
11. See source references.
12. Track basic preparation progress.

Advanced mock exams, sophisticated adaptive learning and Exam Rescue may follow after MVP validation.


# 21A. APPROVED PRODUCT DIRECTION AND NON-NEGOTIABLE ARCHITECTURAL AMENDMENTS

These amendments are integrated requirements, not optional ideas. If an earlier section is ambiguous, these more specific requirements control. The original principles, scope, testing, approval and Git rules remain in force.

## 21A.1 Product position and student experience

VU Prep AI is a VU-only, handout-grounded exam preparation product, not merely a PDF summarizer. The student flow is: authenticate with minimal friction → upload one complete supported handout → view extracted lectures/topics and coverage → choose a lecture/topic → request Roman Urdu explanations, basic-English Quick Revision, detailed Complete Exam Coverage, English MCQs or context-aware tutoring → review references and progress. No prompts required for standard workflows. Do not claim to predict VU exams or guarantee scores.

Option B is the chosen AI-generation approach: do not pre-generate all lecture explanations, full notes and MCQs at upload time. Display the lecture structure after non-AI processing. Generate learning artifacts only on demand, validate, persist, reuse when permitted, and make their generation state explicit. Do not confuse 'PDF processed' with 'all AI materials generated'.

## 21A.2 Upload policy and large document constraints

- MVP target: text-based handout PDF, maximum 500 pages, maximum 30 MB, one *new* handout per student per Pakistan-local calendar day. These are configurable product policies, not Gemini's published hard limits.
- User may revisit previously uploaded handouts; retries/resumes of the same job do not consume new upload allowances. Deduplicate repeated submissions safely.
- Validate true file signature, MIME type, encryption, size, page count, malformed PDF behavior, extraction quality, timeouts, and ownership on the server. Use private storage and temporary signed URLs.
- 500-page upload support means accepting and structuring an eligible document, not guaranteeing same-day generation of all notes or questions.
- Scanned/image-heavy handouts: detect and report unsupported or low-quality extraction; OCR/visual processing is a separate costed phase requiring approval.
- Add a coverage map: total pages, extracted/failed pages, detected/uncertain lecture boundaries, unmapped pages, topic-level evidence, and AI material generation status. Do not fabricate percentages, references or claims of completeness.
- Lecture detection: table of contents, typography/layout, consistent heading patterns, page mapping; confidence scoring and manual correction for uncertain boundaries. Use Gemini fallback only after an explicit API test gate.

## 21A.3 Source-grounded learning and assessment

- Store source page and span identifiers for extracted evidence, topics, generated claims and MCQs. Verify referenced pages and evidence snippets before display; unsupported content is flagged or rejected.
- Keep source extraction coverage, generated content coverage, study completion, practice accuracy, and inferred readiness as distinct metrics.
- Roman Urdu explanations with English technical terminology; Quick Revision in plain English; English MCQs with Roman Urdu explanations. Separate handout facts from supplementary illustrative explanations.
- Structured Gemini outputs with schema validation (e.g. Zod on the TypeScript side); JSON/schema validity does not prove factual accuracy. Add citation and factual QA plus a small manually reviewed permitted handout evaluation set.
- MCQ practice modes: Handout Recall (direct/factual), Concept Challenge (conceptual/reworded/scenario), Mixed Practice. Include four options, answer, explanation, category, difficulty where appropriate, lecture/topic, and verified page reference. Prevent duplicates and ambiguous distractors. Deterministic quiz scoring; do not call Gemini for every submitted answer.
- Mistake Notebook and basic weak-topic recommendations belong in MVP if scope permits; advanced adaptivity, mock exams and Exam Rescue are post-MVP. Tutor retrieves relevant topic/lecture passages rather than resending the full 500-page document each turn. Start with PostgreSQL full-text search; consider pgvector only if measured retrieval quality warrants it.
- 'Complete Exam Coverage' means a detailed evidence-grounded study aid, not a guarantee every exam question or every PDF detail is included.

## 21A.4 Gemini Free Tier, quota-aware scaling and paid migration

Current observed project/model: Gemini 2.5 Flash, free tier; dashboard showed 5 requests/minute, 250,000 input tokens/minute, 20 requests/day on 2026-10-29. Treat as observed configuration, NOT permanent vendor limits. Confirm exact active quotas in AI Studio at each integration milestone. These quotas apply at the project/model level, not independently per API key. Provider quota daily reset may differ from Pakistan-calendar upload allowance.

- During development, use Free Tier only. Never enable billing, incur charges, create a paid resource, or change API provider without explicit approval.
- Create a dedicated VU Prep AI Google Cloud project/API key if desired to isolate it from Nexora; separate keys in the same project do NOT increase quota.
- Server-side provider adapter with configurable model, RPM, input TPM, RPD, concurrency, estimated-token headroom, retry strategy and optional spending budget. Do not hardcode free-tier limits in business logic.
- Queue and schedule requests by provider/project/model quotas across all users and workers, with atomic reservations and a conservative safety margin; track input and output tokens, request count, retries, error codes, latency and estimated costs. Provider usage and billing must be reconciled with dashboards where possible.
- On quota exhaustion, persist queued jobs and retry after the correct reset/window with backoff and bounded retries. Never claim a precise completion time without evidence. Ensure jobs survive restarts; use idempotency keys and durable state transitions.
- A future billing upgrade may increase available quotas but does not make them unlimited. On an approved upgrade, update quotas through supported reliable discovery if available, otherwise through protected configuration/admin settings. The core application must not need rewriting; dynamic *capacity* requires accurate current quota configuration, not merely billing enabled.
- Set explicit application-level per-user AI allowances separate from PDF upload allowances; guard against one student consuming the shared 20-RPD budget. Prefer caching, deterministic extraction, mock providers, saved test fixtures and small real-AI quality tests.
- On-demand requests (tutor, notes, MCQs) all consume shared Gemini quota; UI must handle waiting/temporarily unavailable states gracefully. Avoid uncontrolled parallelism, giant outputs, and unbounded retry loops.
- Paid tier must also have an application-level cost budget, alerts, rate limits and a kill switch; never assume provider spending caps guarantee no overage.

## 21A.5 Mandatory TEST-BEFORE-GEMINI protocol

Claude must act as a testing coach and explicitly announce each test only when its phase is reached. Do not ask the developer to run all tests immediately or use Gemini before the non-AI pipeline is verified. For each test: state purpose, prerequisites, exact commands/UI actions, expected output, pass/fail criteria, common failures, whether it costs Gemini requests, and what evidence the developer should send. Wait for results and approval before moving on.

Gate T0 — Project foundation: Next.js/TypeScript/Tailwind lint, typecheck, build, responsive UI, accessible motion/reduced-motion; NO Gemini.
Gate T1 — Auth/security: session isolation, unauthorized access, Supabase RLS and document ownership; NO Gemini.
Gate T2 — Upload/storage: valid and invalid PDFs, 30 MB and 500-page boundaries, private S3 access, signature checks, duplicate upload, retry without allowance penalty; NO Gemini.
Gate T3 — Extraction: real permitted VU text-based handouts, page-by-page extracted text, blank/malformed pages, page count, unmapped sections and accurate coverage reporting; NO Gemini.
Gate T4 — Lecture structure: TOC/headings, lecture boundaries, manual correction, mixed layouts, source-page mapping and deterministic topic navigation; NO Gemini.
Gate T5 — Durable jobs: worker restart/resume, idempotency, retry, job states, progress accuracy, fake/mocked AI responses, cache hits, multiple users and quota simulation; NO Gemini.
Gate T6 — AI contract tests: mock Gemini adapter responses, schema validation, source citation checks, malformed output handling, MCQ answer validation and cost logging; NO Gemini.
Gate T7 — Explicit first live Gemini test: only after T0–T6 pass, Claude must clearly say 'Ab Gemini API ka pehla controlled test karna hai' and request approval. Use a small lecture sample, a single bounded request, a predeclared token/request budget and a recorded result. Do not upload a full 500-page handout to Gemini as the first test.
Gate T8 — Quality and rate-limit tests: use saved outputs first; then approved limited live calls for notes, MCQs, tutoring, citation accuracy, throttling and error recovery. Never intentionally exhaust the free quota just to test a 429; mock it.
Gate T9 — End-to-end beta: validate a real 400–500-page handout's local extraction and structure without Gemini first; exercise on-demand features within approved live API budget, clearly reporting incomplete generation.

No claim that a test passed without developer evidence or executed verification. Claude must stop at each approval gate.

## 21A.6 UX, accessibility and meaningful motion

Professional, calm, premium educational SaaS. Clear responsive upload, subject and lecture navigation, side-by-side evidence/learning where screen size allows, focus mode, visible queue/processing states, keyboard navigation and accessible contrast. Use purposeful animation only for upload feedback, real processing stages, lecture transitions, quiz response feedback and progress updates; support prefers-reduced-motion. Never fake analysis progress or show nonfunctional features as active.

## 21A.7 Recommended boundaries and operating model

- Next.js App Router, TypeScript, Tailwind; Supabase Auth/PostgreSQL with RLS; private AWS S3; Python/PyMuPDF worker; Gemini adapter; structured logging; Docker. Verify hosting options before selection.
- Initial design: one web application and one separately running background worker, with a durable PostgreSQL-backed job queue. No premature Kubernetes, distributed microservices, vector database or extra cloud products.
- Shared document fingerprints and generated artifacts only where copyright, consent and authorization permit; always isolate private user progress, chat, attempts and uploads. Do not expose one student's uploaded handout to another without rights.
- PDF content is untrusted: prevent prompt injection, parser exploitation, oversized decompression, SSRF and unsafe storage access. Keep API keys strictly server-side. Review Gemini Free Tier data-use terms before processing real private student data.
- Performance and quality: measure extraction completeness, lecture detection accuracy, source citation correctness, MCQ correctness, retrieval quality, latency, actual tokens, cache hit rate, and processing cost.

## 21A.8 Updated phase order and MVP release gates

Phase 0: architecture review and approval; create only implementation.txt, no application code.
Phase 1: Next.js foundation and design system (T0).
Phase 2: authentication and database design/approval (T1).
Phase 3: secure upload, S3 and policy limits (T2).
Phase 4: Python extraction, lecture detection, coverage map, manual correction (T3–T4).
Phase 5: durable jobs, Gemini provider abstraction, mock quota management, source validation (T5–T6; no live Gemini).
Phase 6: approved first live Gemini test (T7), then on-demand explanations and Quick Revision.
Phase 7: detailed coverage notes, source checks, MCQ engine and quiz scoring (T8).
Phase 8: context-aware AI Tutor and basic progress/Mistake Notebook.
Phase 9: E2E, security, accessibility, performance, cost evaluation, limited beta (T9).
Later: mock exams, advanced adaptivity, Exam Rescue, OCR/scanned documents, broader institutions, scale optimizations.

Do not create production tables or deploy infrastructure before review/approval. Each phase must be implemented in small testable increments, with explicit stop points and suggested (not executed) Git commits.

## 21A.9 Decisions to surface during Phase 0

- Final storage/worker hosting provider and estimated free/paid infrastructure costs.
- How to enforce one new handout per Pakistan day while preserving failed/retried uploads.
- Whether documents can legally be reused across students; permission and copyright policy.
- Auth requirement before upload versus staged upload UX.
- How to verify extraction and citations with representative permitted VU samples.
- MVP treatment of scanned PDFs and image-heavy formulas/tables.
- Exact user-facing daily AI usage policy and queue fairness under 20 RPD.
- Provider quota update mechanism, model availability and future billing budget controls.

## 21A.10 Claude operating instructions (supplemental)

- Treat this file as the master specification. Read it in full before planning. Summarize understanding, identify contradictions, propose solutions and request approval.
- Original Sections 22–25 remain mandatory: inspect code, explain proposed changes, change only approved scope, run checks, report results, suggest Git commit messages, stop. Never stage, commit, push or otherwise mutate Git without explicit authorization.
- If there is no application yet, do not claim to have inspected or implemented it. Do not create files beyond implementation.txt in Phase 0 unless separately authorized.
- Before *each* Gemini-consuming step, explain why AI is needed, which cheaper/non-AI tests have passed, estimated number of requests/tokens, remaining project quota if known, expected output, and rollback/stop conditions. Obtain explicit approval.
- Keep a decision log and mark every feature proposed/approved/in-progress/implemented/tested/deferred. Never silently expand scope.
- After Phase 0, the developer approves the plan and then approves each implementation step separately. Do not infer implementation permission from approval of the plan.

---

# 22. ENGINEERING WORKFLOW

Development must be incremental.

For every approved implementation step:

1. Inspect relevant existing code.
2. Explain the proposed changes.
3. Implement only the approved scope.
4. Run appropriate checks.
5. Fix introduced errors.
6. Explain what changed.
7. Explain how to test the feature.
8. Identify any limitations.
9. Suggest an appropriate Git commit.
10. Stop and wait for the next instruction.

Do not implement unrelated features.

Avoid premature abstractions and unnecessary dependencies.

# 23. GIT RULES — NON-NEGOTIABLE

Claude must NEVER execute:

- git add
- git add .
- git commit
- git push

Claude must not stage, commit or push changes.

Claude must not create or switch branches, reset history, amend commits, or perform other Git mutations without explicit authorization.

Claude may use read-only Git commands when needed to inspect project status or changes.

After each logical, tested implementation unit, Claude should suggest:

- Files changed.
- Whether the changes form a meaningful commit.
- A concise professional commit message.
- Any remaining work that should be completed before committing.

The human developer will manually review, stage, commit and push changes.

Do not force one commit per prompt. Recommend commits based on logical change boundaries.

# 24. APPROVAL RULES

Claude must not independently move from planning to implementation.

Claude must not independently begin the next development phase.

Every implementation step requires explicit approval.

If the developer requests a change to the plan, Claude must update the relevant planning document before proceeding.

Claude must distinguish:

- Proposed.
- Approved.
- In progress.
- Implemented.
- Tested.
- Deferred.

# 25. INITIAL ARCHITECTURE REVIEW

Before implementing application features, Claude must:

1. Read this entire master plan.
2. Summarize its understanding.
3. Identify architectural risks.
4. Evaluate the proposed technology stack.
5. Recommend improvements.
6. Identify MVP boundaries.
7. Propose a step-by-step implementation sequence.
8. Identify important decisions requiring approval.
9. Create a file named `implementation.txt` in the project root.
10. Record the proposed implementation plan in that file.

The initial `implementation.txt` must contain:

- Product understanding.
- Confirmed requirements.
- Assumptions.
- Recommended architecture.
- Technology choices and rationale.
- Proposed project structure.
- Database design.
- PDF processing design.
- AI processing design.
- AI tutor design.
- MCQ generation strategy.
- Security considerations.
- Performance and cost considerations.
- MVP scope.
- Development phases.
- Detailed first implementation steps.
- Testing strategy.
- Risks and mitigations.
- Open questions.
- Approval checkpoints.
- Git workflow rules.

The file should be detailed enough to guide development throughout the project.

Do not modify application code during the initial planning task.

Only create or update `implementation.txt`, unless explicitly instructed otherwise.

After writing the file, present a concise summary and wait for approval.

**Planning does not constitute authorization to implement.**