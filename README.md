# EX-02-Cross-Platform-Prompting-Evaluating-Diverse-Techniques-in-AI-Powered-Text-Summarization

## AIM
To evaluate and compare the effectiveness of prompting techniques (zero-shot, few-shot, chain-of-thought, role-based) across different AI platforms (e.g., ChatGPT, Gemini, Claude, Copilot) in a specific task: text summarization.

## Scenario:
You are part of a content curation team for an educational platform that delivers quick summaries of research papers to undergraduate students. Your task is to summarize a 500-word technical article on "The Basics of Blockchain Technology" using multiple AI platforms and prompting strategies.

Your goal is to determine which combination of prompting technique + platform provides the best summary in terms of:

Accuracy

Coherence

Simplicity

Speed

User experience

## Algorithm
1. STEP 1: INITIALIZATION
       Initialize EvaluationMatrix as empty 2D Map (Platforms x PromptStages)
       Define Evaluation Rubric for Metrics (Scale 1-5 for quality, exact measurement for Latency & WordCount)

    2. STEP 2: PROGRESSIVE PROMPT CONSTRUCTION
       FOR EACH stage IN PromptStages DO:
           Construct Prompt(stage) by adding constraints:
           - Basic: Direct task statement
           - Role: Persona injection
           - Context: Target audience & application scenario
           - Constraint: Length & jargon rules
           - Structured Output: Explicit output template & schema
       END FOR

    3. STEP 3: MULTI-PLATFORM TEST EXECUTION
       FOR EACH platform IN Platforms DO:
           FOR EACH stage IN PromptStages DO:
               a. Start Timer (t_start)
               b. Send Prompt(stage) + SourceText to platform API/interface
               c. Receive Response (OutputText)
               d. Stop Timer (t_end)
               e. Calculate Latency = (t_end - t_start)
               
               f. Calculate WordCount = CountWords(OutputText)
               
               g. Store Result in Log(platform, stage, OutputText, Latency, WordCount)
           END FOR
       END FOR

    4. STEP 4: METRIC EVALUATION & SCORING
       FOR EACH (platform, stage) IN Results DO:
           Score_Accuracy   <-- Verify factual consistency against SourceText
           Score_Coherence  <-- Measure logical structure and readability
           Score_Simplicity <-- Evaluate accessibility for 1st-year undergraduates
           Score_Speed      <-- Convert Latency to 1-5 rating
           Score_Compliance <-- Measure adherence to length limits (WordCount)
           
           AggregateScore = WeightedAverage(Score_Accuracy, Score_Coherence, Score_Simplicity, Score_Speed, Score_Compliance)
           
           EvaluationMatrix[platform][stage] = AggregateScore
       END FOR

    5. STEP 5: OPTIMAL CONFIGURATION IDENTIFICATION
       OptimalConfig = MAX(EvaluationMatrix)

    6. STEP 6: REPORT GENERATION
       Generate CSV/Table summarizing cross-platform performance across metrics.
       RETURN EvaluationMatrix, OptimalConfig
## Output

[Prompting Techniques for AI Summarization - Google Gemini.pdf](https://github.com/user-attachments/files/30400659/Prompting.Techniques.for.AI.Summarization.-.Google.Gemini.pdf)


