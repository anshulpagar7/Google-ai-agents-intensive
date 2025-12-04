Day 2A — Agent Tools & Custom Logic (Summary)

In Day 2A, I built a smart currency conversion agent that uses custom Python tools, delegates tasks to specialist agents, and executes real Python code for precise results. This module teaches how to move from simple LLM responses to action-taking, tool-powered AI agents.

🔧 1. Custom Function Tools

I created two Python functions and turned them into ADK tools:

get_fee_for_payment_method(method)

Returns the transaction fee percentage for a payment method.
Example:

"platinum credit card" → 2%

"bank transfer" → 1%

get_exchange_rate(base_currency, target_currency)

Returns the exchange rate between currencies (simulated).
Example:

USD → INR → 83.58

USD → EUR → 0.93

These follow ADK best practices:

Structured return values

Docstrings

Type hints

Clear error handling

🤖 2. Currency Conversion Agent

This agent:

Calls both custom tools

Checks for errors

Combines the results

Produces a detailed final answer

It can explain:

Fee percentage

Fee amount

Remaining amount after fee

Final conversion

Exchange rate used

This is already more advanced than a normal LLM.

🧮 3. Calculation Agent (Agent Tool)

Since LLMs often make mistakes with math, I created a specialist calculation agent:

Its only job is to output pure Python code

No explanations, no text

Uses BuiltInCodeExecutor to run the code safely

Ensures perfect arithmetic accuracy

Example behavior:

Currency agent → asks for code

CalculationAgent → returns code block

Code executor → runs code → gives exact numbers

🧩 4. Enhanced Currency Agent

Finally, I created an enhanced version of the currency agent that:

Uses function tools (fee + exchange rate)

Uses AgentTool(calculation_agent) for math

Delegates complex calculation tasks

Follows a strict instruction protocol

Gives a clean, audited breakdown of the result

This simulates a real-world financial conversion workflow.

🎯 Key Concepts Learned

Function tools

Agent tools (agents calling agents)

Built-in code execution

Retry logic with HttpRetryOptions

Tool orchestration and error handling

Designing safe business logic for agents

🚀 TL;DR

Day 2A taught me how to turn AI agents into action-takers by giving them custom tools, math-safe execution via Python, and multi-agent delegation. This is real production-level agent engineering.
