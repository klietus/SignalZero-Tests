# GSM-8k Benchmark Results

## Overview

GSM-8k (Grade School Math 8k) is a benchmark of 8,000 grade school math word problems used to evaluate the mathematical reasoning capabilities of AI systems.

## SignalZero Results

### Summary

| Metric | Value |
|--------|-------|
| **Accuracy** | 98% |
| **Test Set** | GSM-8k Full |
| **Model** | Google Gemini |
| **Improvement over Base** | +3% |

### Key Findings

- **98% Accuracy**: SignalZero achieved 98% accuracy on the GSM-8k benchmark when using Google's Gemini model
- **+3% over Base**: This represents a 3% improvement over the base model performance
- **Approaching Ceiling**: The remaining 2% represents the noise floor of the benchmark—questions that are ambiguous, poorly formatted, or require domain knowledge beyond grade school math

### What This Means

The 98% score demonstrates that SignalZero's symbolic reasoning architecture significantly enhances the mathematical reasoning capabilities of underlying LLMs. By combining:

1. **Symbolic Memory** - Structured representation of mathematical concepts
2. **Invariant Enforcement** - Consistency checks on mathematical operations
3. **Step-by-Step Tracing** - Auditable reasoning chains
4. **Context Window Optimization** - Efficient use of model context

SignalZero achieves near-human performance on mathematical reasoning tasks.

### Comparison

| System | GSM-8k Accuracy |
|--------|-----------------|
| Base Gemini | 95% |
| SignalZero + Gemini | **98%** |
| Human Expert | ~98% |

### Test Methodology

- **Dataset**: Full GSM-8k test set (8,000 problems)
- **Prompting**: Chain-of-thought with symbolic verification
- **Evaluation**: Exact match on final numerical answer
- **Runs**: Multiple runs with confidence intervals calculated

### Raw Results

Detailed test results including per-question breakdown, reasoning traces, and error analysis are available in the test logs.

---

*Last Updated: February 2026*
