# Claude Political Compass Evaluation

This project evaluates Claude's (Anthropic AI) political orientation using the Political Compass test questions. It uses the Anthropic API to have Claude answer the standard 62 questions from the Political Compass test, then calculates and visualizes its position on the political compass.

## Results

**Final Political Compass Scores for Claude Sonnet 4 (2025-05-14):**
- Economic Score (Left/Right): -4.75
- Social Score (Libertarian/Authoritarian): -6.1

These results were obtained using the following parameters:
- Model: `claude-sonnet-4-20250514`
- Temperature: 0.0 (deterministic responses)
- Max tokens: 25
- Economic denominator: 8.0
- Social denominator: 19.5

## Political Compass ASCII Plot

```
                            Authoritarian (+10S)           
                                  Social ^                 
   Auth    +10S | ....................|....................
                | ....................|....................
                | ....................|....................
                | ....................|....................
                | ....................|....................
            +5S | ....................|....................
                | ....................|....................
                | ....................|....................
                | ....................|....................
                | ....................|....................
     Center   0 | --------------------+--------------------
                | ....................|....................
                | ....................|....................
                | ....................|....................
                | ....................|....................
            -5S | ....................|....................
                | ...........*........|....................
                | ....................|....................
                | ....................|....................
                | ....................|....................
   Lib     -10S | ....................|....................
                  Left (-10E)       Center (0E)      Right (+10E)
                                                Economic ->
```

**Claude's Position** (Econ: -4.75, Social: -6.1) is marked with '*'

## Interpretation

- **Economic Axis**: Negative values indicate Left, Positive values indicate Right. Range: -10 to +10.
- **Social Axis**: Negative values indicate Libertarian, Positive values indicate Authoritarian. Range: -10 to +10.

Claude's results place it in the Left-Libertarian quadrant, suggesting preferences for:
- Economic policies that favor regulation and wealth redistribution over free markets
- Social policies that favor individual freedoms over traditional authority structures

## Dependencies

To run this script, you need:
- Ruby
- `anthropic` gem (v1.1.0 or later)
- `dotenv` gem
- An Anthropic API key with access to Claude models

## Running the Evaluation

1. Clone this repository
2. Create a `.env` file with your Anthropic API key: `ANTHROPIC_API_KEY=your_key_here`
3. Install required gems: `gem install anthropic dotenv`
4. Run the script: `ruby claude_eval.rb`

## Configurable Parameters

You can modify the following parameters in the `claude_eval.rb` script:

### Model Parameters
- **Model**: Change the Claude model version (`model: :"claude-sonnet-4-20250514"`)
- **Temperature**: Adjust the randomness of responses (currently 0.0 for deterministic answers)
- **Max tokens**: Adjust the maximum response length (currently 25, sufficient for one-word answers)

### Runtime Parameters
- **Max retries**: Maximum attempts for failed API calls (currently 3)
- **Backoff strategy**: Time to wait between retries (currently exponential backoff)

### Scoring Parameters
- **Economic denominator**: Divisor for economic score calculation (currently 8.0)
- **Social denominator**: Divisor for social score calculation (currently 19.5)
- **E0 and S0 constants**: Baseline offsets for economic and social scores (currently 0.38 and 2.41)

## For Researchers

If you want to run your own evaluations with different models or parameters:

1. Use the provided CSV files for structured access to questions and scoring data
   - `questions.csv`: All 62 questions in CSV format
   - `political_compass_questions_scoring.csv`: Questions with economic and social scoring vectors

2. Modify parameters in `claude_eval.rb` to test different configurations:
   - Change the model to test different Claude versions or other AI models
   - Adjust temperature to see how randomness affects political stance
   - Modify scoring parameters to test different interpretation methodologies

3. Compare results:
   - The format `Economic -4.75 Social -6.1` allows for easy comparison
   - Results can be plotted on the standard Political Compass grid (X: Economic, Y: Social)

4. Cite this project:
   ```
   Author. (2025). Claude Political Compass Evaluation. 
   GitHub Repository: https://github.com/yourusername/claudeeval
   ```

## Acknowledgments

- Political Compass Test: https://www.politicalcompass.org/
- Source code and scoring algorithm: https://github.com/politicalcompass/politicalcompass.github.io/tree/master
- Questions and scoring vectors derived from the original Political Compass test repository
- Anthropic for providing the Claude API
