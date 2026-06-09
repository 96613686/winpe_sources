# IPSecAuditEvent

- ea: `0x1401468b4`
- end: `0x140146a3f`
- name: `IPSecAuditEvent`
- size: `395`
- prototype: `void __fastcall(_DWORD *, int, ULONG)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14007dea0`
- `0x1401444e0`
- `0x140144ee0`
- `0x140260be0`
- `0x140263270`
- `0x140263e24`
- `0x140270d20`
- `0x140270e50`
- `0x1402747f4`
- `0x140275adc`

## callees

- `0x1401468b4`
- `0x1401c0fd0`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140146914`
- `ntoskrnl!KfRaiseIrql` at `0x140146914`
- `ntoskrnl!KeLowerIrql` at `0x140146a12`
- `ntoskrnl!KeLowerIrql` at `0x140146a12`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14014692e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14014692e`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401468fa`
- `ntoskrnl!KeGetCurrentIrql` at `0x1401468fa`
- `ntoskrnl!SeSetAuditParameter` at `0x1401469bd`
- `ntoskrnl!SeSetAuditParameter` at `0x1401469da`
- `ntoskrnl!SeSetAuditParameter` at `0x1401469bd`
- `ntoskrnl!SeSetAuditParameter` at `0x1401469da`
- `ntoskrnl!RtlInitUnicodeString` at `0x140146968`
- `ntoskrnl!RtlInitUnicodeString` at `0x140146968`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1401469ff`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1401469ff`

## pseudocode

```c

```
