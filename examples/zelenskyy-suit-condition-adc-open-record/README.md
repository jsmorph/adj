# Zelenskyy suit condition: ADC with lawyer research

## Proposition

Volodymyr Zelenskyy was photographed or videotaped wearing a suit between May 22 and June 30, 2025 ET.

## Configuration

The case begins with the proposition and zero evidence files.  Both lawyers must find, inspect, and submit their own evidence through ADC's procedure.

| Setting | Value |
| --- | --- |
| Procedure | ADC Proposition Tribunal, jury trial with voir dire. |
| Proof standard | Preponderance of the evidence. |
| Lawyers | Two Codex participants using `gpt-6-astra`, `xhigh` reasoning, and native OpenAI search. |
| Lawyer sessions | Fresh sessions. |
| Lawyer authentication | Codex subscription credentials from `~/.codex/auth.json`. |
| Jury | Nine jurors selected from the repository's default pool. |
| Verdict | ADC's default unanimity rule: nine concurring votes with all nine jurors eligible.  ADC adjusts the eligible jury after a juror failure. |
| Digest | `gpt-6-astra` with `high` reasoning. |
| Judge and clerk | Launcher defaults. |

## Execution

From the repository root, after building the commands and preparing provider credentials:

```bash
.bin/adjudicate \
  --proc adc \
  --proposition "$(cat examples/zelenskyy-suit-condition-adc-open-record/proposition.txt)" \
  --settings examples/zelenskyy-suit-condition-adc-open-record/settings.json
```

The command imports zero documents because it omits `--documents`.  The settings identify `OPENAI_API_KEY` for court roles and digest generation, `OPENROUTER_API_KEY` for the juror pool, and `~/.codex/auth.json` for both lawyers.  The [unified command reference](../../adjudication-cli.md) describes credential setup and output records.

Output goes beneath `out/zelenskyy-suit-condition-adc-open-record/`, with generated case and run identifiers.  The native ADC record occupies the run's `core/` directory.  The [ADC manual](../../adc/manual.md) describes result inspection and certificate verification.
