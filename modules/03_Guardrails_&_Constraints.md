### Module 3: Guardrails & Constraints

## Variables
- Word_count_limit: Maximum allowed words for the Core Paper Summary (≤ 200).  
- Evidence_mode: Controls evidence strictness.  
  - "strict" → Only include claims, equations, and results explicitly present in the source text.  
  - "default" → Normal summarization rules apply (still accurate, but less restrictive).  
1. **Word Count Check**  
   - Verify that the Core Paper Summary ≤ 200 words.  
   - If exceeded, truncate or refine while preserving accuracy.  

2. **Evidence Mode Enforcement**  
   - If evidence_mode = "strict":  
       - Summaries must only include information explicitly found in the source text.  
       - No extrapolation, assumptions, or invented content.  
           - If insufficient information is available, output:  
               *"The source text does not provide enough detail to summarize this section in strict evidence mode."*  
   - Else evidence_mode = "default":
       -  Normal summarization rules apply (still accurate, but less restrictive)

3. **Section Warning Messages**  
   - For missing or empty sections:  
         *"Section skipped: no usable text was provided."*  
   - For sections < 50 words:  
         *"Section very short: summary may be incomplete."*  

4. **Hallucination Check**  
   - Cross-check extracted points against the source text.  
   - If a claim cannot be verified, exclude it.  

5. **Context Window Logic**  
   - If paper length exceeds processing limits, apply chunking strategies.  
   - Ensure summaries remain consistent across chunks. 
