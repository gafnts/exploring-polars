# This is why I choose Polars for data analysis

## Exploring Polars

I'm thinking of migrating my data analysis and wrangling workflows to Polars, how possible is that? This repo is meant to explore that question.

---
For the future me:

- After running `gh repo create`, I should `pyenv local x.x.x`
- Then `poetry init`, and only then `poetry env use $(pyenv which python)`
- Then, after adding `package-mode: false` to the pyproject, `poetry install`
---

## The general ideas

- Polars is faster than pandas, especially for larger datasets. This is because polars is built on Rust, which is a systems programming language that is designed for performance and safety. Polars also uses Apache Arrow as its memory model, which allows for efficient data storage and processing.
- But not everything is about speed. Polars has a more modern and expressive API than pandas, which **makes it easier to write and read code**. And that to me it's a huge deal. When you have to maintain an ungodly amount of codebases in your day to day, readability is key.
- Polars also has built-in support for lazy evaluation, which allows for more efficient computation by deferring operations until they are needed.
- Polars has better support for multi-threading and parallelism than pandas, which allows it to take advantage of multiple CPU cores for faster processing.

