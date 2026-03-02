# CMPUT 802 — Blockchain Assignment

Build a Python client that generates keys, mines a block, and submits it to the class blockchain.

## Quick Start

**Prerequisites:** Python 3.11+ and [uv](https://docs.astral.sh/uv/)

```bash
git clone https://github.com/Lucklyric/mm802w26-blockchain-tutorial-student.git
cd mm802w26-blockchain-tutorial-student
uv sync
```

## Configuration

Edit `config.py` with your details:

```python
EMAIL = "you@ualberta.ca"
STUDENT_RANDOM = [your, chosen, numbers]    # 3-5 random numbers from Google Form
INSTRUCTOR_RANDOM = [x, y, z]               # announced in class
SERVER_URL = "http://<SERVER_IP>"            # provided in class
```

## Exercises

Work through each part in order. Each file has `TODO` comments with hints.

| # | File | What You Implement | Run |
|---|------|--------------------|-----|
| 1 | `part1_keygen.py` | Generate ECDSA key pair from your identity | `uv run python part1_keygen.py` |
| 2 | `part2_explore.py` | Read blockchain state via REST API | `uv run python part2_explore.py` |
| 3 | `part3_create_block.py` | Construct a block linking to the chain tip | `uv run python part3_create_block.py` |
| 4 | `part4_mine.py` | Mine with Proof of Work (~65k hash guesses) | `uv run python part4_mine.py` |
| 5 | `part5_submit.py` | Sign and submit your block to the server | `uv run python part5_submit.py` |

## Grading

When the server ledger shows your email with `status = 1`, you're done. Check the Chain Explorer on the server to verify your block.

## Resources

All hosted on the class server (URL provided in class):

- `/tutorial/overview.html` — Assignment overview
- `/tutorial/` — Step-by-step tutorial
- `/tutorial/explorer.html` — Live chain explorer
- `/docs` — API documentation

## Troubleshooting

- **"Invalid index" or "Invalid previous_hash"** — Someone mined before you. Just re-run `part5_submit.py`, it re-fetches the latest block and re-mines automatically.
- **Keys not found** — Run `part1_keygen.py` first to generate your key pair.
- **Connection refused** — Check that `SERVER_URL` in `config.py` matches the server IP provided in class.
