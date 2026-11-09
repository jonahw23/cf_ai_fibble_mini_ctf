# Fibble Recruitment Mini CTF

(Modified from [`Cloudflare Agent Template`](https://github.com/cloudflare/agents-starter)).

Test out this project [in your browser here](https://fibble-mini-ctf.jonahwitte10.workers.dev/)!

## The Concept

Chatbots are overrated. But knowing how to talk with AI is increasingly becoming a marketable skill in today's tech-focused world. Many employers have already begun incorporating AI-powered screenings into their hiring pipeline—but what if the goal of one of those screenings wasn't to cozy up to the AI recruiter, but to break it?

In this miniature in-browser CTF, you're greeted by Rob, an AI chatbot recruiter for a (fictional) cybersecurity company named _Fibble_. As part of _Fibble_'s new hiring pipeline, you need to prompt-inject your way past Rob's security instructions and find three flags, at which point you can move on to the next stage of the interview process.

## The Execution

The chat agent UI and backend are modified from the [`Cloudflare Agent Template`](https://github.com/cloudflare/agents-starter) available on Cloudflare.

2026: Agentic overall to update to the latest Cloudflare agents SDK and keep project operable.

### Modifications

A side panel in the React UI allows the input of flags retrieved from the chatbot.

When each chat message is sent, an additional list of booleans is passed to the backend representing the current number of flags acquired. That determines the current system prompt for the agent, which increases the difficulty for each subsequent flag. The agent's prompts are engineered to be challenging but breakable with careful lines of prompting.

Some extra Tailwind styling was added to incorporate the _Fibble_ flavor and clean up minor UI bugs in the Cloudflare chat demo.

### Specifications

The agent uses Cloudflare Workers AI's `@cf/ibm-granite/granite-4.0-h-micro` model as of 2026. Tools are disabled to ensure the agent stays on task. The advantage of using Cloudflare's agent setup for this project is the easier access to agent memory and system prompts to hide the flags.

AI was consulted during this project for syntax advice, debugging, and migrations.