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

## Sample Inputs and Expected Outputs

Run the notebook cell and enter one sample when `Paste a support ticket:` appears. Rerun the cell for each test. The table shows what the program prints after you submit the input.



| Scenario | Sample input | Expected output |
|---|---|---|
| Valid ticket | `I was charged twice for my subscription.` | `Text ready for the model: I was charged twice for my subscription.` |
| One email address | `I cannot log in. Email me at customer@example.com.` | `Text ready for the model: I cannot log in. Email me at [EMAIL].` |
| Two email addresses | `Please update my email from old@example.com to new@example.org.` | `Text ready for the model: Please update my email from [EMAIL] to [EMAIL].` |
| Empty ticket | Press Enter without typing anything. | `Ticket cannot be empty.` |
| Whitespace-only ticket | Type five spaces, then press Enter. | `Ticket cannot be empty.` |
| Oversized ticket | Paste a string containing 2,001 characters. | `Ticket must be 2,000 characters or fewer.` |

To generate the oversized sample, run this in a separate notebook cell,
then copy the printed string into the ticket input box:

```python
print("A" * 2001)
```

The current notebook demonstrates input validation and email redaction.
`Text ready for the model` is printed by Python. LLM summarization and
output validation are planned.
