# CInputGlobals::UpdateWakeOnInputDeviceTypesFromRegistry(void)

- ea: `0x1400c0310`
- end: `0x1400c0536`
- name: `?UpdateWakeOnInputDeviceTypesFromRegistry@CInputGlobals@@QEAAXXZ`
- size: `550`
- prototype: `void __fastcall(CInputGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1401774f4`

## callees

- `0x14000bed0`
- `0x14000c970`
- `0x1400bf6cc`
- `0x1400c0310`
- `0x140238160`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400c03b4`
- `ntoskrnl!ZwOpenKey` at `0x1400c03b4`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c040c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c04da`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c040c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400c04da`
- `ntoskrnl!ZwClose` at `0x1400c0420`
- `ntoskrnl!ZwClose` at `0x1400c0525`
- `ntoskrnl!ZwClose` at `0x1400c0420`
- `ntoskrnl!ZwClose` at `0x1400c0525`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c0373`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c03dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c04ab`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c0373`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c03dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c04ab`

## string_xrefs

- `0x1400c0358`: `\Registry\Machine\SYSTEM\INPUT`

## pseudocode

```c

```
