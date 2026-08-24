# GitHub Project Evaluator

An evidence-first Codex skill for rating GitHub projects, skills, and AI agents. It converts inspectable evidence into a transparent 0–5 star rating across realness, practical usefulness, stability, trust, and project health.

It is designed to avoid two common mistakes: treating popularity as proof, and treating a lack of evidence as a claim of failure. Every material conclusion is labelled as fact, inference, assumption, or unknown, and every rating includes a confidence level.

## Install

Place the `github-project-evaluator` directory in your Codex skills directory, then ask Codex to evaluate a repository URL or local path.

## Example

```text
Use $github-project-evaluator to evaluate https://github.com/owner/repository. Give me an evidence-backed rating and tell me whether I should adopt it, pilot it, watch it, or avoid it for now.
```

## License

Apache-2.0. See [LICENSE](LICENSE).
