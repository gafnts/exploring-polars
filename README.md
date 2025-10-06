# This is why I choose Polars for data analysis

## Exploring Polars

I'm thinking of migrating my data analysis and wrangling workflows to Polars, how possible is that? This repo is meant to explore that question.


## The general ideas

- Polars is faster than pandas, especially for larger datasets. This is because polars is built on Rust, which is a systems programming language that is designed for performance and safety. Polars also uses Apache Arrow as its memory model, which allows for efficient data storage and processing.
- But not everything is about speed. Polars has a more modern and expressive API than pandas, which **makes it easier to write and read code**. And that to me it's a huge deal. When you have to maintain an ungodly amount of codebases in your day to day, readability is key.
- Polars also has built-in support for lazy evaluation, which allows for more efficient computation by deferring operations until they are needed.
- Polars has better support for multi-threading and parallelism than pandas, which allows it to take advantage of multiple CPU cores for faster processing.

## Some insights

- Type safety and schema declaration: Polars' `schema_overrides` parameter embodies a modern, type-safe approach inspired by TypeScript and Pydantic. Unlike pandas' string-based `dtype` parameter, Polars uses first-class types (`pl.Categorical`, `pl.Int32`, `pl.Date`) that are more discoverable and type-checker friendly.
- Less post-processing required: Where pandas often requires additional data cleaning and type coercion after loading, Polars enforces your schema contract upfront. The data is correct by the time it enters your workflow.
- Fail-fast philosophy: Polars errors immediately on type mismatches at schema definition time, not some transformations later. This Rust-inspired "catch errors early" approach prevents silent bugs and data quality issues from propagating through your pipeline.
- Expression API Superiority: Polars' expression-based transformations `(pl.col("price").filter(pl.col("quantity") > 0).mean())` are more composable and readable than pandas' assignment-based approach. It reads like SQL but with type safety.

When pandas still wins: The ecosystem integration (`sklearn`, `statsmodels`) and team familiarity still make pandas the pragmatic choice for some scenarios. But for new projects and production pipelines, Polars' strictness becomes a feature, not a limitation.

Polars is what pandas would look like if designed today with Rust's type system discipline and lessons from the TypeScript revolution. It makes the invisible visible and respects the programmer's intelligence.
