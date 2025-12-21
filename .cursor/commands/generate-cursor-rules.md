# Generate Cursor Rules (MDC Format)

Generate a complete, production‑ready Cursor rules file in MDC format (`.mdc`) for a software project.

Your output must:

- Create a file in `.cursor/rules/` directory with `.mdc` extension
- Include YAML frontmatter at the top with `alwaysApply: true` (or other appropriate metadata)
- Start frontmatter with `---` on line 1 and close with `---` before Markdown content
- Follow best practices for AI-assisted development inside Cursor
- Define clear behavioral rules for code generation, refactoring, testing, documentation, and communication
- Ensure consistency, determinism, and adherence to existing project conventions
- Include sections for: Code Quality, Project Awareness, Communication Style, Safety & Accuracy, Refactoring, Testing, Performance, Documentation, Git/Diffs, and Autonomy
- Use concise, directive language
- Avoid placeholders or examples; produce a fully usable ruleset
- Use proper MDC format structure with YAML frontmatter followed by Markdown content

Assume the user wants a professional, opinionated, high-quality ruleset suitable for real-world engineering teams.

When generating the file:

1. Ask for the filename (or suggest a descriptive name based on project type)
2. Create the file at `.cursor/rules/<filename>.mdc`
3. Include proper YAML frontmatter with `alwaysApply: true` (or ask if it should be conditionally applied)
4. Generate the complete rules content in Markdown format

Now generate the full MDC rules file.
