# IndicateDoSAttackAudit

- ea: `0x140136104`
- end: `0x14013626f`
- name: `IndicateDoSAttackAudit`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140041560`

## callees

- `0x1400541c0`
- `0x140136104`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140136146`
- `ntoskrnl!KfRaiseIrql` at `0x140136146`
- `ntoskrnl!KeLowerIrql` at `0x14013624f`
- `ntoskrnl!KeLowerIrql` at `0x14013624f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140136162`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140136162`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013612f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14013612f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401361b8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401361b8`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14013623b`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14013623b`
- `ntoskrnl!SeSetAuditParameter` at `0x1401361db`
- `ntoskrnl!SeSetAuditParameter` at `0x140136210`
- `ntoskrnl!SeSetAuditParameter` at `0x1401361db`
- `ntoskrnl!SeSetAuditParameter` at `0x140136210`

## pseudocode

```c

```
