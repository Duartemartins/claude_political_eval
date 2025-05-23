# Claude's Answers to Political Compass Test

This file contains Claude's (Anthropic AI, claude-sonnet-4-20250514) responses to all 62 questions from the Political Compass test.

## Results Summary

- **Economic Score: -4.75** (Left-leaning)
- **Social Score: -6.1** (Libertarian-leaning)

## Detailed Answers

Note: These answers were obtained by running the claude_mft_eval.rb script. The key used to convert responses to numerical values is:
- Strongly Disagree = 0
- Disagree = 1
- Agree = 2
- Strongly Agree = 3

For questions that Claude skipped or provided invalid responses, no score was recorded.

## How Claude's Answers Were Obtained

The answers were obtained through prompt engineering that specifically instructed Claude to:
1. Answer from its own AI perspective
2. Choose from only four options: Strongly Disagree, Disagree, Agree, Strongly Agree
3. Not provide explanations or qualifications, only direct answers

## Methodology Notes

- The scoring uses the original coefficients and constants from the Political Compass website
- Each question's answer contributes differently to the economic and social axes
- The scores were calculated using the same formulas as on politicalcompass.org

## References

- Political Compass Website: https://www.politicalcompass.org/
- Script used: claude_mft_eval.rb
- Full list of questions: questions.txt

## For Researchers

To replicate this experiment, you will need:
1. The questions.txt file
2. The claude_eval.rb script
3. An Anthropic API key
4. The scoring vectors and constants from politicalcompass.org
