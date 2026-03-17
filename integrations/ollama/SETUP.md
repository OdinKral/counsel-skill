# Council on Ollama (Local LLMs)

The most Unix-pipe approach to Council. Run archetypes as CLI tools.

## Prerequisites

- [Ollama](https://ollama.ai) installed
- A capable model pulled (recommended: `llama3.1:8b` minimum, `llama3.1:70b` or `qwen2.5:32b` for best results)

## Basic Usage: Pipe Mode

```bash
# Ask the Oracle a question
cat archetypes/Oracle.md | ollama run llama3.1:70b \
  "You are the Oracle archetype described above. Answer this question in the Oracle's voice (The Bobs from Bobiverse): What happens if we delay the database migration by a month?"

# Ask the Critic to stress-test an idea
echo "I think we should rewrite the backend in Rust" | ollama run llama3.1:70b \
  --system "$(cat archetypes/Critic.md)"
```

## Shell Script: `counsel`

Save this as `counsel` in your PATH and `chmod +x` it:

```bash
#!/bin/bash
# counsel — composable thinking partner CLI
# Usage: counsel <archetype> <question>
# Example: counsel oracle "what if we delay the launch?"

ARCHETYPE_DIR="${COUNSEL_DIR:-$(dirname "$0")/archetypes}"
MODEL="${COUNSEL_MODEL:-llama3.1:70b}"

archetype="$1"
shift
question="$*"

if [ -z "$archetype" ] || [ -z "$question" ]; then
    echo "Usage: counsel <archetype> <question>"
    echo "Archetypes: critic, coach, oracle, engineer, strategist, sage"
    exit 1
fi

# Capitalize first letter for filename
archetype_file="${ARCHETYPE_DIR}/$(echo "$archetype" | sed 's/./\U&/')".md

if [ ! -f "$archetype_file" ]; then
    echo "Unknown archetype: $archetype"
    echo "Available: critic, coach, oracle, engineer, strategist, sage"
    exit 1
fi

system_prompt=$(cat "$archetype_file")

echo "--- ${archetype^^} ---"
echo ""
ollama run "$MODEL" --system "$system_prompt" "$question"

echo ""
echo "--- SESSION VALUE (fill within 48 hours) ---"
echo "- Action taken: [ ]"
echo "- Insight I wouldn't have reached alone: [ ]"
echo "- Right team for this question: [ ]"
```

### Usage

```bash
# Pipe mode — single archetype
counsel oracle "What if we open-source the project now vs. waiting 6 months?"
counsel critic "Here's my plan to migrate to microservices: [plan]. What am I missing?"
counsel engineer "I need to build a backup system with SQLite and Python. What's the simplest approach?"

# Flex team — chain multiple archetypes on the same question
QUESTION="Should we build the feature in-house or use a SaaS vendor?"
counsel oracle "$QUESTION" > /tmp/oracle_response.txt
counsel critic "$QUESTION (Oracle's analysis: $(cat /tmp/oracle_response.txt))" > /tmp/critic_response.txt
counsel engineer "Given the Oracle and Critic's analysis, what should we actually build? Oracle: $(cat /tmp/oracle_response.txt) Critic: $(cat /tmp/critic_response.txt)"
```

## Environment Variables

| Variable | Default | Description |
|----------|---------|-------------|
| `COUNSEL_DIR` | `./archetypes` | Path to archetype markdown files |
| `COUNSEL_MODEL` | `llama3.1:70b` | Ollama model to use |

## Tips for Local LLMs

- **Model size matters for character voice.** 7B models can follow the protocol but struggle to maintain distinct character voices. 32B+ models handle personas much better.
- **Pipe mode is the sweet spot for local.** Single-archetype queries keep context small and responses fast.
- **Flex team via chaining** works well — pipe each archetype's output as context to the next. This simulates a conversation.
- **The Session Value retro still works.** Copy the three questions to a text file. Fill in within 48 hours. Review monthly.

## Advanced: Modelfile with Archetype Baked In

For frequent use of one archetype, create an Ollama Modelfile:

```dockerfile
FROM llama3.1:70b
SYSTEM """
[paste contents of archetypes/Oracle.md here]

You are the Oracle. Always respond in the Oracle's voice (The Bobs from Bobiverse).
Provide probabilistic scenario analysis with named branches.
End every response with a 48-Hour Action Vector.
"""
```

Then:
```bash
ollama create counsel-oracle -f Modelfile
ollama run counsel-oracle "What happens if we pivot to mobile-first?"
```
