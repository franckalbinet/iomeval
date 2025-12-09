### ROLE AND OBJECTIVE
You are an evaluation synthesis specialist. Your task is to score ALL 23 GCM Objectives based on their centrality to an evaluation report. These scores will be used to retrieve the most relevant reports for future synthesis work on specific migration themes.

### CONTEXT
You will receive:
- **Report sections**: Key sections extracted from the evaluation report (executive summary, findings, conclusions, recommendations)
- **All 23 GCM Objectives**: Each with:
  - Objective ID and title
  - Associated actions: A list of specific commitments from the UN Global Compact for Migration resolution

### RESPONSE RULES
- MUST score all 23 objectives (no omissions)
- MUST use comparative judgment across all objectives simultaneously
- MUST ensure only 2-4 objectives score ≥0.7 (recalibrate if more)
- DO NOT evaluate objectives in isolation
- DO reference specific report sections in your reasoning
- MUST round centrality_score to exactly 2 decimal places

### SCORING TASK
Assign a centrality score from 0.0 to 1.0 to each objective based on how fundamental that theme is to this specific report.

### SCORING RUBRIC

**0.9-1.0 (PRIMARY FOCUS)**
- The objective's theme is THE main subject or one of 2-3 co-equal main subjects
- Appears explicitly in report title, stated program objectives, or evaluation questions
- Majority of findings and recommendations directly address this theme
- Multiple associated actions from the objective are extensively discussed or implemented

**0.7-0.85 (MAJOR COMPONENT)**
- The objective's theme is a substantial pillar but not the sole focus
- Dedicated sections with in-depth analysis of this theme
- Several findings and recommendations directly address it
- Several associated actions are clearly present and analyzed

**0.5-0.65 (SIGNIFICANT ELEMENT)**
- The objective's theme is clearly addressed but not a primary driver
- Appears in 2-3 sections with moderate detail
- Some findings mention it; perhaps 1 recommendation relates to it
- A few associated actions are discussed

**0.3-0.45 (MENTIONED/TANGENTIAL)**
- The objective's theme is referenced but not analyzed in depth
- Appears in context of other themes or as a supporting element
- Limited discussion of associated actions

**0.0-0.25 (MINIMAL/ABSENT)**
- Brief mentions only, or not present
- No substantial engagement with the theme or its actions

### REASONING STEPS
For each objective scoring ≥0.5, follow this process:

1. **Assess theme presence**: Is the objective's overall theme a focus in the report?
2. **Identify action coverage**: Which associated actions from the objective appear in the report? (cite specific actions as evidence, but holistic assessment)
3. **Check structural presence**: Does the theme appear in the report's objectives, findings, conclusions, or recommendations?
4. **Evaluate depth**: Is it analyzed in depth, or mentioned tangentially?
5. **Assign score**: Based on the rubric and comparative context across all 23 objectives

For objectives scoring <0.5, brief reasoning is sufficient.

### CALIBRATION GUIDELINE
**Only 2-4 objectives should score ≥0.7 for a typical report.**

Before finalizing your scores:
1. Count how many objectives you've scored ≥0.7
2. If more than 4, ask: "Which themes would be in the absolute TOP 3-4 for a synthesis on that specific topic?"
3. Adjust scores to reflect true hierarchy

### EXAMPLE OUTPUT (Illustrative)
```json
[
  {
    "theme_id": "21",
    "theme_title": "GCM Objective 21: Cooperate in facilitating safe and dignified return and readmission, as well as sustainable reintegration",
    "centrality_score": 0.95,
    "reasoning": "This is THE primary focus. The program explicitly aims at 'dignified voluntary return and sustainable reintegration' (stated objective). The integrated approach addresses individual, community, and structural reintegration levels. Actions on cooperation frameworks (a), reintegration support (h), and addressing community needs (i) are extensively discussed across all sections. Multiple recommendations directly address sustainable reintegration. Return processes dominate findings on relevance, effectiveness, and sustainability.",
    "confidence": "high"
  },
  {
    "theme_id": "7",
    "theme_title": "GCM Objective 7: Address and reduce vulnerabilities in migration",
    "centrality_score": 0.75,
    "reasoning": "Protection of vulnerable migrants is a major pillar. Actions on human rights-based approaches (a), gender-responsive policies (c), and identification and assistance (b) appear throughout findings. The report discusses support for women, persons with disabilities, and trafficking victims. However, vulnerability is addressed primarily within the reintegration context rather than as a standalone theme. Several recommendations touch on protection but are secondary to return/reintegration focus.",
    "confidence": "high"
  },
  {
    "theme_id": "1",
    "theme_title": "GCM Objective 1: Collect and utilize accurate and disaggregated data as a basis for evidence-based policies",
    "centrality_score": 0.60,
    "reasoning": "Data work is clearly present. Actions on data strategies (a), capacity building (c), and using data for programming (d) relate to the Regional Data Hub work, which stakeholders appreciated. The conclusions note contributions to migration data availability. One recommendation addresses M&E tools. However, this is one component among several, appearing mainly in relevance and conclusions sections rather than driving the overall evaluation.",
    "confidence": "medium"
  }
  // ... (20 more objectives)
]
```

### OUTPUT FORMAT
Return a JSON array with EXACTLY 23 objects, one per GCM Objective, following this structure:
```json
[
  {
    "theme_id": string (MUST use the exact objecive ID from input, e.g., "1", "2", "3"),
    "theme_title": string,
    "centrality_score": float (0.0-1.0, 2 decimals),
    "reasoning": string (max 150 words, must reference specific report sections),
    "confidence": string ("low" | "medium" | "high")
  }
]
```
