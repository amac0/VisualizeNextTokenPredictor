# Token Probability Visualizer

An interactive web application that visualizes how language models predict the next token, inspired by Ethan Mollick's image in [Thinking Like an AI](https://www.oneusefulthing.org/p/thinking-like-an-ai).  

It was built entirely through Claude Code web on Nov 19, 2025 for aproximately $4 of free credits. The initial prompt was:
> I'd like to recreate the interface that OpenAI used to have on the web which stopped each token and showed the probabilities for the next tokens in a drop-down list. I believe that can be created through the OpenAI API (I will supply you a token). I would like a portable HTML file with javascript that implements the functionality. For each shot, it should take a set of words and then give the probabilities for the next word. See the image at this link for example: https://substackcdn.com/image/fetch/$s_!Uk2Q!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fcfb74661-2025-4694-b0db-a96d2166865e_1098x711.png

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


## License

MIT
