# IndicateDoSAttackAudit

- ea: `0x140135fc4`
- end: `0x14013612f`
- name: `IndicateDoSAttackAudit`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400412c0`

## callees

- `0x140053f20`
- `0x140135fc4`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140136006`
- `ntoskrnl!KfRaiseIrql` at `0x140136006`
- `ntoskrnl!KeLowerIrql` at `0x14013610f`
- `ntoskrnl!KeLowerIrql` at `0x14013610f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140136022`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140136022`
- `ntoskrnl!KeGetCurrentIrql` at `0x140135fef`
- `ntoskrnl!KeGetCurrentIrql` at `0x140135fef`
- `ntoskrnl!RtlInitUnicodeString` at `0x140136078`
- `ntoskrnl!RtlInitUnicodeString` at `0x140136078`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1401360fb`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1401360fb`
- `ntoskrnl!SeSetAuditParameter` at `0x14013609b`
- `ntoskrnl!SeSetAuditParameter` at `0x1401360d0`
- `ntoskrnl!SeSetAuditParameter` at `0x14013609b`
- `ntoskrnl!SeSetAuditParameter` at `0x1401360d0`

## pseudocode

```c

```
