```
PROMPT: 76b41ad3276c003bf0a1de2e8af91c643b48aa1dac6a0d0a2ba232c68070a51d
MODEL: sonnet
TEMPERATURE: 0
```

1. Passed 11/12 problems. ([log](https://github.com/abrasumente233/ab_challenge_eval/blob/main/users/abrasumente233/log.txt)).
2. Full prompt: [link](https://github.com/abrasumente233/ab_challenge_eval/blob/main/users/abrasumente233/prompt.txt).
3. Total cost for all 12 problems: $1.952 ($0.163 per problem)
4. Three additional runs were performed, achieved 10/12, 11/12, and 11/12 respectively. (on my own eval, hopefully they are the same, as I don't have any more credits left to test)

To run the eval, put OpenRouter API key in `~/.config/openai.token` and run `node install && node main.mjs abrasumente233`.

extra notes:

1. The original challenge allows a maximum of 32k output tokens, but Claude models are limited to 4k tokens per response. To accommodate this limitation, Claude was prompted to continue its response when necessary. ([changes](https://github.com/abrasumente233/ab_challenge_eval/commit/66934af5a86db1844b09d849fe896f0a122abbdd)).
2. Sonnet model from OpenRouter API used (same pricing as official API afaik?).
3. Haiku model tested, scoring ~6/12. Extra tinkering needed.
4. Current prompt is bloated; could be further minimized.

## A::B Eval

This is a simple evaluator for the [A::B](https://gist.github.com/VictorTaelin/8ec1d8a0a3c87af31c25224a1f7e31ec) prompting challenge.

To use it, add your Anthropic/OpenAi key to your home directory:

    ~/.config/anthropic.token
    ~/.config/openai.token

Then, add 2 files to this directory:

    ./users/YOUR_NAME/prompt.txt # the system prompt
    ./users/YOUR_NAME/model.txt  # the model name

Then, clone this repository, perform `npm install` and run `node main.mjs YOUR_NAME`.
