**Narrow Single-Department Pilot Unlocks Faster MRD Chart Closure and Lower Claim Denials**

**1.1 Problem: Post-Discharge Manual Checks Create Billing Bottlenecks and Accreditation Risk**

In medium-to-large secondary and tertiary care hospitals across India, every inpatient case sheet arriving in the Hospital Medical Records Department (MRD) after physical patient discharge must pass two sequential, largely paper- or scan-based manual reviews before final archiving and insurance claim submission: (1) a completeness check verifying physician signatures, discharge summary presence, operative notes, consent forms, and mandatory fields required under National Accreditation Board for Hospitals & Healthcare Providers (NABH) standards, and (2) a clinical coding check translating free-text diagnostic and procedural narratives into standardized World Health Organization ICD-10 codes. Today, this workflow suffers from four severe operational failure modes:

**•	Slow and inconsistent ICD-10 coding (15 to 30+ minutes per complex chart):** Because clinical notes contain unstandardized physician abbreviations, specialty-specific shorthand, and multi-morbidity narratives, two coding officers reviewing similar surgical charts frequently assign divergent CDC ICD-10-CM codes. Inaccurate or unspecified codes directly trigger Third-Party Administrator (TPA) and insurance claim rejections (MediCodio AI).

**•	Labor-intensive deficiency chasing across wards:** MRD Deficiency Officers manually flip through multi-page scanned or physical files to spot missing signatures or incomplete discharge advice, then chase busy clinicians via one-on-one phone calls or physical ward rounds—a repetitive process prone to human oversight and multi-day delays (PMC Audit Study).

**•	Blind First-In-First-Out (FIFO) queue processing:** All discharge records sit in an undifferentiated queue regardless of financial claim value, TPA submission deadline, or regulatory audit sensitivity, causing high-value cashless/reimbursement files and high-audit-risk records to stall behind routine low-complexity cash charts.

**•	Downstream hospital-wide ripple effects:** MRD backlogs delay insurance cash flow, stall medico-legal record issuances, impede statutory communicable disease and mortality reporting, and expose the hospital to non-compliance citations during NABH 6th Edition and Joint Commission International (JCI) surveillance audits.

**1.2 Target User and Customer Segments**
Chart Ready AI is engineered specifically for the three interconnected operational roles inside the hospital Health Information Management (HIM) / MRD function:
**•	Primary User — MRD Coding Officers:** Credentialed medical coders who read discharge summaries and operative notes to assign WHO ICD-10 diagnosis and procedure codes for TPA/insurance billing and statutory reporting.

**•	Secondary User — MRD Deficiency / Completion Officers:** Operations staff responsible for auditing case sheets for missing clinician signatures, incomplete clinical summaries, and unsigned consent forms prior to final chart closure.

**•	Primary Beneficiary / Economic Buyer — MRD Department Head / Health Information Manager:** Owns department-wide Turnaround Time (TAT), coding accuracy rates, TPA claim denial metrics, and continuous audit-readiness for NABH Accreditation.

**1.3 Product Concept:** Chart Ready AI
Chart Ready AI is an AI-assisted workflow copilot and triage layer—not an autonomous black-box billing system—built for the Hospital MRD. Operating within an access-controlled hospital Virtual Private Cloud (VPC), the system ingests discharge summaries and executes three tightly scoped functions around a mandatory Human-in-the-Loop (HITL) review gate:

**•	Automated Completeness Classification:** Evaluates each chart against a fixed checklist of mandatory clinical documentation elements (summary present and signed, final diagnosis, operative/procedure note, condition at discharge, and follow-up advice), classifying the record as Complete or Deficient and specifying the exact deficiency category.

**•	Constrained ICD-10 Code Recommendation with Evidence Grounding:** Suggests the most probable diagnosis and procedure codes (constrained in the MVP to the 30–50 highest-frequency codes in the pilot department), paired with a calibrated confidence score and highlighted verbatim text spans from the clinical note for a human coder to Accept, Edit, or Reject.

**•	Risk- and Value-Adjusted Queue Triage:** Dynamically orders the MRD review queue by financial claim value, TPA SLA urgency, and NABH audit sensitivity so senior coders and clinicians resolve high-impact files first.

**1.4 Why AI Is the Right Lever Over Simpler Non-AI Alternatives**

Traditional deterministic software—such as regex keyword scripts, mandatory EHR checkboxes, or BI completeness dashboards—fails to resolve the core MRD bottleneck. Keyword-matching rules break immediately when confronted with physician-specific phrasing, synonymous clinical terminology (e.g., 'acute calculous cholecystitis' vs. 'inflamed gallbladder with impacted stone'), clinical negations ('ruled out peritonitis'), and non-standard abbreviations. Similarly, a conventional EHR checkbox dashboard can verify whether a text field contains characters, but it cannot evaluate clinical semantic sufficiency—such as whether a three-word entry in the follow-up field satisfies NABH Continuity of Care standards or whether an operative narrative justifies a complex complication code. Domain-grounded Large Language Models (LLMs) combined with Retrieval-Augmented Generation (RAG) provide the semantic comprehension needed to map variable clinical prose to structured coding ontologies while surfacing uncertainty for human verification.


**1.5 Decisive Leadership Recommendation: Proceed to Controlled Single-Department Pilot**

**EXECUTIVE DECISION:** PROCEED TO NARROW PILOT (DO NOT SCALE HOSPITAL-WIDE YET)
Among the five capstone decision gates (Explore / Prototype / Pilot / Scale / Reject), Team 056 recommends proceeding to a 12-week Controlled Single-Department Pilot restricted to General Surgery Discharge Summaries in a single hospital unit. We explicitly reject immediate hospital-wide scaling or full EMR auto-posting because clinical coding carries high financial and regulatory error costs. Full multi-department scale must remain gated until the pilot proves: (a) >=25% reduction in chart completion TAT against baseline, (b) >=88% top-3 ICD-10 recall across the top 30–50 surgical codes, (c) zero unauthorized PHI egress under India's Digital Personal Data Protection (DPDP) Act 2023, and (d) sustained coder override vigilance without automation complacency.




|Capstone Dimension|Strategic Choice for Chart Ready AI|Managerial Rationale & Risk Defense|
|---|---|---|
|Primary Problem|Manual completeness & ICD-10 checks taking 15–30+ mins/chart in FIFO queues|Eliminates TPA claim delays, coding rejections, and pre-audit NABH compliance backlogs|
|First Wedge (MVP)|Single department (General Surgery), 1 doc type (Discharge Summary), Top 30–50 ICD-10 codes|Contains clinical vocabulary variance; proves Extract -> Suggest -> Confirm -> Route loop safely|
|Technical Path|API-First Enterprise LLM + Vector RAG inside Hospital VPC (No custom model training)|Avoids ₹50L+ upfront ML annotation/training cost; focuses differentiation on workflow & HITL logic|
|Trust & HITL Model|Zero auto-billing; mandatory Coder Accept/Edit/Reject & Physician Sign-off on deficiencies|Prevents hallucinated codes from reaching TPAs; preserves legal clinician accountability|
|Launch Decision|Proceed to 12-Week Pilot; Block full scale until evaluation gates pass|Balances rapid operational learning with strict healthcare governance and DPDP Act compliance|
