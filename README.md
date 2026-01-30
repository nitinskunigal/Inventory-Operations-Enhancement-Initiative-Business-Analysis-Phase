# Inventory Operations Enhancement - A Business Analysis Initiative

## Executive Summary

MapleDash Grocers, a simulated e-grocery retailer, operates a multi-warehouse fulfillment network across the Greater Toronto Area, supporting high-volume, time-sensitive customer demand. While core systems such as the Inventory Management System (IMS), Warehouse Management System (WMS), and Order Management System (OMS) are in place, inventory operations rely heavily on manual coordination, delayed updates, and supervisor-driven controls.

A data-driven assessment revealed that operational challenges stem not from missing systems, but from execution gaps between physical warehouse activities and system-recorded inventory states. These gaps manifest as inventory inaccuracies, ATP overselling, uneven stock distribution, frequent replenishment exceptions, and preventable picking disruptions.

This Business Analysis project defines a targeted IMS enhancement approach focused on system-directed execution, automated inventory updates, and exception-based human intervention across five core processes:
- Receiving  
- Putaway  
- Cycle Counting  
- Replenishment  
- Order Picking  

The solution deliberately avoids full system replacement or enterprise-grade integrations, aligning with MapleDash’s operational maturity and growth trajectory.

The outcome is a disciplined, scalable inventory execution model that improves inventory accuracy, fulfillment reliability, and operational efficiency without introducing unnecessary complexity or cost.

---

## Table of Contents

- [1. Problem Statement and Strategic Context](#1-problem-statement-and-strategic-context)
- [2. Strategic Business Objectives](#2-strategic-business-objectives)
- [3. How Data Analysis Informed the Business Analysis](#3-how-data-analysis-informed-the-business-analysis)
- [4. Solution Approach](#4-solution-approach)
- [5. Estimated Benefits and Expected Outcomes](#5-estimated-benefits-and-expected-outcomes)
- [6. Limitations, Constraints, and Future Enhancement Opportunities](#6-limitations-constraints-and-future-enhancement-opportunities)
- [7. Key Business Analysis Artifacts and Traceability](#7-key-business-analysis-artifacts-and-traceability)
- [8. Repository Navigation and Links](#8-repository-navigation-and-links)

## 1. Problem Statement and Strategic Context

MapleDash’s fulfillment model depends on accurate inventory visibility, reliable replenishment, and disciplined execution across multiple warehouses. As order volumes and SKU complexity increased, operational processes failed to scale at the same pace.

The core issue is not missing systems, but misalignment between physical inventory movements and system updates. Receiving, putaway, replenishment, and cycle counts often complete physically before systems are validated.
- Execution Gaps: These timing gaps distort ATP, leading to overselling and pick-time shortages.
- Hidden Risk: Aggregate inventory looks healthy, but SKU-level imbalances and localized stockout risk are hidden.
- Operational Impact: Because system data can’t be fully trusted, supervisors step in to manually resolve routine discrepancies, creating a reactive operating model.
- Strategic Need: The organization doesn’t need new platforms. It needs stronger execution discipline, clearer system control points, and workflows that guide routine decisions automatically.

Strategically, MapleDash does not need a full system replacement or advanced automation to resolve these challenges. What is required is stronger execution discipline, system-directed workflows for routine activities, and clear exception thresholds that focus human effort where it adds the most value.

This initiative directly addresses that need while remaining aligned with MapleDash’s size, maturity, and growth trajectory.

---

## 2. Strategic Business Objectives

The primary objective of the MapleDash Inventory Management System (IMS) enhancement initiative is to improve inventory accuracy, operational reliability, and replenishment effectiveness while maintaining system simplicity and scalability appropriate for a mid-sized e-grocery organization.
The following business objectives are Specific, Measurable, Achievable, Relevant, and Time-bound (SMART):

**Objective 1 – Improve Inventory Accuracy**  
- *Aligned KPIs*: % SKUs Oversold (ATP < 0), % SKUs Below ROP, % SKUs Below Safety Stock, Median Sellable Coverage (Days), Total ATP Qty, Inventory Turnover (Annual), Days of Inventory, Days of Cover
- *Specific*: Reduce discrepancies between physical stock and system-recorded inventory levels.
- *Measurable*: Decrease inventory variance incidents (reflected through ATP overselling and ROP breaches) by at least 30%.
- *Achievable*: Through system-directed cycle counting, real-time validations, and automated inventory updates.
- *Relevant*: Inventory inaccuracies directly contribute to stockouts, overselling, and customer dissatisfaction.
- *Time-bound*: Within 3 months of IMS enhancement rollout.

**Objective 2 – Reduce Replenishment Exceptions and Stockout Risk**  
- *Aligned KPIs*: % SKUs Below ROP, % SKUs Below Safety Stock, Days of Cover, Median Sellable Coverage (Days), Total ATP Qty, Avg. Daily Orders, Total Order Qty
- *Specific*: Proactive replenishment for high-demand and high-risk SKUs; reduce firefighting.
- *Measurable*: Reduce the percentage of SKUs falling below Reorder Point (ROP) by 20% and below Safety Stock by 15%.
- *Achievable*: By introducing system-driven replenishment triggers aligned with demand patterns and SKU classification (ABC–XYZ).
- *Relevant*: Frequent replenishment exceptions currently increase supervisor workload and stockout risk.
- *Time-bound*: Within 4 months of implementation.

**Objective 3 – Increase Inbound Processing Reliability**  
- *Aligned KPIs*: % SKUs Oversold (ATP < 0), Total ATP Qty, Days of Cover, Total Orders, Total Revenue, Inventory Turnover
- *Specific*: Improve the consistency and timeliness of inventory (QOH and ATP) updates.
- *Measurable*: Ensure 95% of inbound receipts update Quantity on Hand (QOH) and ATP within 15 minutes of receiving completion.
- *Achievable*: Through automated receipt validation, ASN matching, and reduced manual data entry.
- *Relevant*: Delayed inbound updates cause ATP inaccuracies and downstream fulfillment issues.
- *Time-bound*: Within 2 months of go-live.

**Objective 4 – Reduce Manual Intervention and Supervisor Workload**  
-	*Aligned KPIs*: % SKUs Oversold (ATP < 0), % SKUs Below ROP, Median Sellable Coverage (Days)
-	*Specific*: Minimize the need for manual reviews and exception handling by supervisors.
-	*Measurable*: Reduce supervisor intervention events related to inventory discrepancies by 25%.
-	*Achievable*: By filtering exceptions to true anomalies and automating standard inventory updates.
-	*Relevant*: Supervisors currently spend excessive time resolving preventable inventory issues.
-	*Time-bound*: Within 3 months post-implementation.

**Objective 5 – Improve Inventory Availability Without Increasing Stock Levels**  
-	*Aligned KPIs*: Days of Cover, Median Sellable Coverage (Days), Total Inventory Value, Inventory Turnover (Annual), Value Expiring < 30 Days
-	*Specific*: Improve effective inventory availability using existing stock levels; no capital inflation.
-	*Measurable*: Improve Days of Cover efficiency (optimize coverage without increasing Total Inventory Value).
-	*Achievable*: Through better SKU-level stock distribution and improved ATP accuracy rather than additional purchasing.
-	*Relevant*: MapleDash aims to improve service levels without tying up additional working capital.
-	*Time-bound*: Within 6 months of enhancement deployment.

**Objective 6 – Establish a Foundation for Data-Driven Inventory Decisions**  
-	*Aligned KPIs*: All 18 KPIs
-	*Specific*: Enable consistent, reliable metrics for operational decision-making and governance.
-	*Measurable*: Standardize KPI definitions and enable monthly operational reviews using consistent inventory dashboards.
-	*Achievable*: By aligning IMS outputs with Power BI-based reporting already in use.
-	*Relevant*: Data inconsistency currently limits trust in reports and hinders proactive management.
-	*Time-bound*: Within 6 months of implementation.

---

## 3. How Data Analysis Informed the Business Analysis

Before defining requirements or solutions as part of business analysis, a dedicated Data Analysis was conducted during discovery using Power BI as the analytical tool to establish a fact-based understanding of MapleDash’s current-state operations. The data analysis did not propose solutions. Instead, it surfaced where execution breaks down and where operational risk accumulates, enabling informed BA decisions.

Key contributions of the data analysis phase included:

- Identifying inventory accuracy risk through ATP overselling, SKU-level stock imbalances, and delayed adjustments  
- Revealing demand volatility patterns using ABC–XYZ classification to highlight high-risk SKUs  
- Exposing uneven inventory distribution via Days of Cover vs. Median Sellable Coverage analysis  
- Highlighting warehouse-level throughput imbalance across fulfillment centers  
- Providing supplier reliability context (OTD%, lead time variability, supplier concentration) as an external risk factor, not a system failure  

These insights directly shaped future state process design, particularly where system control points were required. In the next few slides, we’ll look at the detailed insights & data-indicated root causes derived from data analysis.

In short, data analysis diagnosed the problem space, while business analysis translated those signals into structured requirements and solution design. 

🔗 **[Data Analysis GitHub Repository](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Data-Analysis-Phase)**

---

## 4. Solution Approach

The proposed solution is a **process-led IMS enhancement**, not a technology overhaul. It strengthens how inventory decisions are executed, validated, and recorded across the warehouse network.

### Core Design Principles

**System-Directed Execution**  
Routine decisions such as receiving validation, putaway location selection, replenishment triggers, cycle count task generation, and pick task creation are system-directed. Basically, this removes reliance on individual judgment for routine actions and execution becomes consistent across warehouses.

**Automation Inventory Updates at Control Points**  
Inventory updates occur automatically only after validated execution steps, ensuring Quantity on Hand (QOH) and Available-to-Promise (ATP) reflect physical reality rather than assumptions. Basically, this directly addresses ATP overselling and delayed inventory synchronization.

**Exception-Based Human Intervention**  
Supervisors are engaged only when predefined tolerance thresholds are breached. Routine activities proceed without manual approval, reducing firefighting and cognitive load.

**Single Version of Inventory Truth**  
Inventory deductions and adjustments occur at clearly defined control points, eliminating duplicate updates and reconciliation confusion. Basically, this stabilizes downstream processes like picking and replenishment.

**Pragmatic Integration**  
Data synchronization between IMS, WMS, and OMS is lightweight and reliability-focused, avoiding real-time orchestration complexity. Basically, this keeps the solution aligned with company’s current maturity.

Together, these principles convert inventory operations from reactive and manual to disciplined, scalable, and auditable while remaining appropriate for a mid-sized e-grocery organization.

---

## 5. Estimated Benefits and Expected Outcomes

Based on current-state baselines identified during data analysis, the proposed solution is expected to deliver measurable operational improvements within six months of implementation, assuming disciplined adoption.

### Key Expected Outcomes

- **Improved Inventory Turnover:** Inventory Turnover is expected to increase from 6.5x to approximately 8.0x, driven by better alignment between demand velocity and stock placement, reduced overstocking in slow-moving categories, and faster  execution cycles.  
- **Reduced ATP Overselling:** The percentage of SKUs oversold (ATP < 0) is expected to drop from 2.9% to below 1%, as inventory updates are synchronized with validated execution events.  
- **Lower Replenishment Risk:** SKUs below Reorder Point (ROP) are expected to reduce from 17.3% to under 10%, reflecting more timely and consistent replenishment triggers.  
- **Lean Inventory Position:** Days of Inventory are expected to decrease from 56 days to 50 days or less, improving working capital efficiency without increasing stockout risk.  
- **Tighter SKU-Level Coverage:** Median Sellable Coverage is expected to reduce from 33 days to approximately 30 days, indicating more balanced inventory distribution across SKUs.  

These outcomes represent execution efficiency gains, not demand growth assumptions, and are consistent with the scope and responsibility of an IMS-led process enhancement initiative.

---

## 6. Limitations, Constraints, and Future Enhancement Opportunities

This Business Analysis initiative was intentionally scoped to address execution discipline, inventory accuracy, and operational reliability within MapleDash’s current systems landscape and organizational maturity. While the proposed solution delivers measurable benefits within a short horizon, it does not attempt to solve every adjacent opportunity. The following outlines key limitations by design, followed by realistic next steps aligned with MapleDash’s longer-term strategy.

### 6.1 Intentional Limitations and Scope Constraints

Several areas were deliberately excluded to ensure feasibility, adoption, and time-to-value:

- **No full system replacement or ERP consolidation**: The project assumes continued use of existing IMS, WMS, and OMS platforms. Replacing or consolidating systems was deemed high-risk, cost-intensive, and misaligned with MapleDash’s current growth stage.
- **No real-time or enterprise-grade integrations**: Data synchronization focuses on reliability and control points rather than real-time orchestration. This avoids architectural complexity while still improving execution accuracy.
- **No advanced forecasting, AI, or optimization engines**: Demand forecasting, predictive replenishment, and machine-learning-based optimization were intentionally excluded. The root issues identified were execution-driven, not forecast-driven.
- **Supplier behavior not treated as a controllable lever**: Supplier reliability metrics were used strictly as inbound risk context. Contract renegotiation, sourcing strategy changes, or supplier performance improvement initiatives fall outside this project’s mandate.
- **Power BI used as a diagnostic and monitoring tool, not a decision engine**: Dashboards support visibility and monitoring but do not replace operational workflows or system-directed controls.
These constraints ensure the solution remains practical, implementable, and defensible within a six-month horizon.

### 6.2 Near-Term Enhancements (Post-Stabilization)

Once execution discipline and system trust are stabilized, MapleDash can extend value through incremental enhancements:

- **Operationalized BI monitoring**: Transition Power BI dashboards from diagnostic use to operational governance, including alerting for ATP risk, replenishment exceptions, and expiry exposure.
- **Rule refinement and tuning**: Fine-tune tolerance thresholds, exception rules, and category-specific replenishment logic based on post-implementation performance trends.
- **Expanded KPI governance**: Introduce formal KPI ownership, escalation paths, and review cadences to sustain benefits realization beyond initial rollout.
- **Improved data pipelines**: Move from CSV-based extracts toward database-driven reporting and scheduled refresh pipelines as analytical maturity increases.

### 6.3 Medium-Term Strategic Opportunities

With execution foundations in place, MapleDash can pursue broader capability improvements:

- **Advanced replenishment logic**: Incorporate demand seasonality, promotion calendars, and lead time variability into replenishment planning once baseline accuracy is achieved.
- **Supplier segmentation and risk scoring**: Use observed performance data to inform procurement strategy, supplier tiering, and buffer differentiation without immediate contract changes.
- **Network-level inventory balancing**: Introduce systematic inventory rebalancing across fulfillment centers to reduce throughput concentration risk and improve service resilience.
- **Warehouse execution analytics**: Extend analytics into labor productivity, task cycle times, and exception frequency to further optimize warehouse operations.

### 6.4 Long-Term Vision Alignment

In the long term, this initiative positions MapleDash to evolve toward:

- More automated and predictive inventory decision-making
- Tighter integration between planning and execution layers
- Scalable analytics and reporting infrastructure
- Reduced dependency on manual supervision as volume grows

Crucially, these future enhancements build on a stable execution foundation rather than attempting to leap directly to advanced automation. This staged approach ensures MapleDash’s inventory operations evolve in line with business maturity, risk tolerance, and strategic priorities.

---

## 7. Key Business Analysis Artifacts and Traceability

This repository contains a complete, industry-aligned set of Business Analysis artifacts demonstrating traceability from problem identification through solution validation.

### Core Deliverables

- **Business Requirements Document (BRD):** Business objectives, rules, requirements, and success metrics  
- **Process Maps (AS-IS & TO-BE):** Five core inventory processes  
- **Use Case Diagrams & Specifications:** Automation-first actor–system interactions  
- **Product Backlog:** Epics, user stories, acceptance criteria, ownership, and KPI alignment  
- **Traceability Matrix:** Business Requirements → Functional Requirements → User Stories → KPIs  
- **UAT Artifacts:** Scenarios, test cases, defect log, sign-off templates  
- **Low-Fidelity Wireframes:** Operational system interactions for requirement clarity  

---

## 8. Repository Navigation and Links

- **[Data Analysis GitHub Repository](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-Initiative-Data-Analysis-Phase)**  
- **[Interactive Power BI Dashboard](https://app.powerbi.com/view?r=eyJrIjoiZmRmNGRhOGEtN2IyNi00ZWNjLTkxN2YtMmYyMzJhNzNhN2NmIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9)**
- **[Business Case](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-A-Business-Analysis-Initiative/blob/main/BA%20Deliverables/Business%20Case.pdf)**  
- **[Business Requirements Document (BRD)](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-A-Business-Analysis-Initiative/blob/main/BA%20Deliverables/Business%20Requirements%20Document%20(BRD).pdf)**
- **[Stakeholder Analysis & Interview Guide](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-A-Business-Analysis-Initiative/blob/main/BA%20Deliverables/Stakeholder%20Analysis%20%26%20Interview%20Guide.pdf)**
- **[Current State & Future State Process Maps](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-A-Business-Analysis-Initiative/tree/main/BA%20Deliverables/Current%20State%20%26%20Future%20State%20Process%20Maps)**
- **[System Context Diagram](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-A-Business-Analysis-Initiative/blob/main/BA%20Deliverables/System%20Context%20Diagram.png)**
- **[Product Backlog & UAT](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-A-Business-Analysis-Initiative/tree/main/BA%20Deliverables/Product%20Backlog%20%26%20UAT)**
- **[Use Case Diagrams, Use Case Specs, and Wireframes](https://github.com/nitinskunigal/Inventory-Operations-Enhancement-A-Business-Analysis-Initiative/tree/main/BA%20Deliverables/Use%20Case%20Diagrams%2C%20Use%20Case%20Specs%2C%20and%20Wireframes)**
