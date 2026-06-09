# IPSecUpdateOffloadStatus

- ea: `0x1402607c4`
- end: `0x1402609fe`
- name: `IPSecUpdateOffloadStatus`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140265880`

## callees

- `0x1401bf4d0`
- `0x1402607c4`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14026084a`
- `ntoskrnl!ZwOpenKey` at `0x14026084a`
- `ntoskrnl!ZwClose` at `0x1402609d4`
- `ntoskrnl!ZwClose` at `0x1402609d4`
- `ntoskrnl!ZwQueryValueKey` at `0x1402608a0`
- `ntoskrnl!ZwQueryValueKey` at `0x1402608fc`
- `ntoskrnl!ZwQueryValueKey` at `0x140260958`
- `ntoskrnl!ZwQueryValueKey` at `0x1402609b4`
- `ntoskrnl!ZwQueryValueKey` at `0x1402608a0`
- `ntoskrnl!ZwQueryValueKey` at `0x1402608fc`
- `ntoskrnl!ZwQueryValueKey` at `0x140260958`
- `ntoskrnl!ZwQueryValueKey` at `0x1402609b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14026080d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260871`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402608cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260929`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260985`
- `ntoskrnl!RtlInitUnicodeString` at `0x14026080d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260871`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402608cd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260929`
- `ntoskrnl!RtlInitUnicodeString` at `0x140260985`

## string_xrefs

- `0x1402607e7`: `\Registry\Machine\System\CurrentControlSet\Services\IPSEC`
- `0x14026091e`: `EnableHeuristics`

## pseudocode

```c

```
