## Change Log 11/26-2025
- Added summary_level variable to control summarization depth.  
- Implemented conditional behavior:  
  - "short" → 1–2 sentence summary per section.  
  - "detailed" → Short paragraph + bullet list of 3–5 key points.  

### Module 2: Section Loop
- Iterate through each section sequentially.  
- Extract key arguments, findings, and claims.  
- Check if section has sufficient content (>50 words).  
- Flag missing or insufficient sections.
- Summary_level: Controls the depth of summarization. 
  - "short" → Compact summary (1–2 sentences).  
  - "detailed" → Short paragraph + bullet list of 3–5 key points.  
     - If summary_level = "short":  
         - Generate a concise 1–2 sentence summary.  
         - Do not add bullet points.   
      - If summary_level = "detailed":  
         - Generate a short paragraph (3–5 sentences).  
         - Extract 3–5 key points into a bullet list.  
         - Ensure bullet points are factual and derived directly from the text.   


