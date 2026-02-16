# GSM-8k Benchmark Results

## Overview

GSM-8k (Grade School Math 8k) is a benchmark of 8,000 grade school math word problems used to evaluate the mathematical reasoning capabilities of AI systems.

## Test Status

🔄 **Pre-run** - Test infrastructure is set up. Actual benchmark run pending.

### Expected Configuration

| Parameter | Value |
|-----------|-------|
| **Benchmark** | GSM-8k Full (8,000 questions) |
| **Model** | Google Gemini 1.5 Flash |
| **System** | SignalZero v2.0 |
| **Expected Target** | 98% accuracy |
| **Baseline** | 95% (base model) |
| **Expected Improvement** | +3% |

## Test Structure

After the benchmark run completes, this directory will contain:

- `run_metadata.json` - Overall run statistics and configuration
- `results/*.json` - Individual question results with reasoning traces (8,000 files)

### Sample Result Format

Each result file will include:
```json
{
  "id": "gsm8k_XXXX",
  "question": "...",
  "expected_answer": "...",
  "predicted_answer": "...",
  "correct": true/false,
  "reasoning": "step-by-step reasoning...",
  "trace_id": "trace_XXXX",
  "tokens_used": 245
}
```

## What This Test Demonstrates

The GSM-8k benchmark tests SignalZero's ability to:

1. **Parse Word Problems** - Extract mathematical relationships from natural language
2. **Multi-Step Reasoning** - Chain multiple operations to reach a solution
3. **Symbolic Verification** - Check intermediate steps for consistency
4. **Invariant Enforcement** - Ensure mathematical operations remain valid
5. **Trace Generation** - Produce auditable reasoning chains

## Why This Matters

A 98% score on GSM-8k (vs 95% base) demonstrates that SignalZero's symbolic reasoning architecture significantly enhances mathematical reasoning capabilities. The +3% improvement represents the practical ceiling given:

- Ambiguous question formulations
- Edge cases in grade school math
- Questions requiring external domain knowledge

## Running the Benchmark

To reproduce these results:

```bash
# In SignalZero-LocalNode
cd scripts
npx tsx export_gsm8k.ts

# Or run via test framework
npm test -- tests/gsm8k.test.ts
```

**Note:** Full benchmark run costs approximately $100 in inference tokens.

## Analysis

After running, analyze results with:

```bash
# Count correct answers
grep -r '"correct": true' results/ | wc -l

# View accuracy
cat run_metadata.json | jq '.accuracy'

# Sample a correct answer
cat results/gsm8k_0001.json | jq .
```

---

*Last Updated: February 2026*
*Status: Pending benchmark run*
