# Safe GenAI Ticket Summarizer

A beginner-friendly Python project that demonstrates input guardrails
for a GenAI support-ticket workflow.

The current notebook rejects blank tickets and tickets over 2,000
characters. It replaces email addresses that match a regex pattern
with `[EMAIL]` and displays the cleaned text.

**Example input:** I cannot log in. Email me at customer@example.com.

**Example output:** I cannot log in. Email me at [EMAIL].

**Project status:** Input validation and email redaction are implemented.
LLM summarization, ticket categorization, and output validation are planned.
