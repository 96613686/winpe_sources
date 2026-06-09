# IndicateDoSAttackAudit

- ea: `0x14013b260`
- end: `0x14013b3cb`
- name: `IndicateDoSAttackAudit`
- size: `363`
- prototype: `void __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140053e80`

## callees

- `0x140014a90`
- `0x14013b260`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14013b2a2`
- `ntoskrnl!KfRaiseIrql` at `0x14013b2a2`
- `ntoskrnl!KeLowerIrql` at `0x14013b3ab`
- `ntoskrnl!KeLowerIrql` at `0x14013b3ab`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14013b2be`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14013b2be`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013b28b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013b28b`
- `ntoskrnl!SeSetAuditParameter` at `0x14013b337`
- `ntoskrnl!SeSetAuditParameter` at `0x14013b36c`
- `ntoskrnl!SeSetAuditParameter` at `0x14013b337`
- `ntoskrnl!SeSetAuditParameter` at `0x14013b36c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14013b314`
- `ntoskrnl!RtlInitUnicodeString` at `0x14013b314`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14013b397`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14013b397`

## pseudocode

```c

```
