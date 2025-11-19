# Token Probability Visualizer

An interactive web application that visualizes how language models predict the next token, inspired by OpenAI's classic token probability interface.

## Features

- **Interactive Token Selection**: Click any generated token to see alternative predictions with their probabilities
- **Dynamic Regeneration**: Select an alternative token to regenerate all subsequent text from that point
- **Visual Probability Indicators**: Color-coded tokens based on model confidence (green=high, yellow=medium, red=low)
- **Probability Insights**: Hover over tokens to see position, probability, and number of alternatives
- **Undo/History**: Track and revert changes with full history support
- **Advanced Controls**: Adjust temperature, top-p, and presence penalty for customized generation
- **Smooth Animations**: Polished UI with fade transitions and highlight effects

## Usage

1. **Open the File**: Simply open `token-probability-viewer.html` in any modern web browser
2. **Enter API Key**: Paste your OpenAI API key in the designated field
3. **Configure Settings**: Adjust model, max tokens, and sampling parameters as desired
4. **Generate**: Click "Generate with Probabilities" to start
5. **Explore Alternatives**: Click any token to see what else the model considered
6. **Branch and Explore**: Select alternatives to regenerate text and explore different paths

## Requirements

- Modern web browser (Chrome, Firefox, Safari, or Edge)
- OpenAI API key with access to models that support `logprobs` parameter
- Recommended model: `gpt-3.5-turbo-instruct` (default)

## How It Works

The interface makes API calls to OpenAI with the `logprobs` parameter enabled. For each generated token, it retrieves:
- The selected token
- Top N alternative tokens (configurable, default 15)
- Log probabilities for each alternative

When you select an alternative token, the interface:
1. Updates the input prompt to include all tokens up to that point
2. Removes all subsequent tokens
3. Regenerates fresh completions from the new context

This allows you to interactively explore the model's decision-making process and discover alternative narrative paths.

## Tips

- **Experiment with Temperature**: Lower values (0.1-0.5) make the model more focused; higher values (1.5-2.0) make it more creative
- **Use Undo**: Don't be afraid to explore - you can always undo your changes
- **Try Different Prompts**: The default prompt "The best kind of pet is a" is great for exploring alternatives
- **Watch the Colors**: Red/yellow tokens indicate uncertainty - interesting places to explore alternatives!

## Design

Built with a modern shadcn-inspired design system featuring:
- Clean, minimal interface with excellent readability
- Thoughtful spacing and typography
- Smooth transitions and animations
- Accessible color palette

## License

This is a standalone educational tool. Use responsibly with your own OpenAI API key.
