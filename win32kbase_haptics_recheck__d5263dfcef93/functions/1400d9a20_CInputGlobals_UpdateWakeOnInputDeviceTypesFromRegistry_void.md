# CInputGlobals::UpdateWakeOnInputDeviceTypesFromRegistry(void)

- ea: `0x1400d9a20`
- end: `0x1400d9c46`
- name: `?UpdateWakeOnInputDeviceTypesFromRegistry@CInputGlobals@@QEAAXXZ`
- size: `550`
- prototype: `void __fastcall(CInputGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140176794`

## callees

- `0x14005c5d0`
- `0x14005c610`
- `0x1400d8ddc`
- `0x1400d9a20`
- `0x140238b10`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400d9ac4`
- `ntoskrnl!ZwOpenKey` at `0x1400d9ac4`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d9b1c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d9bea`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d9b1c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400d9bea`
- `ntoskrnl!ZwClose` at `0x1400d9b30`
- `ntoskrnl!ZwClose` at `0x1400d9c35`
- `ntoskrnl!ZwClose` at `0x1400d9b30`
- `ntoskrnl!ZwClose` at `0x1400d9c35`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d9a83`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d9aed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d9bbb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d9a83`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d9aed`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d9bbb`

## string_xrefs

- `0x1400d9a68`: `\Registry\Machine\SYSTEM\INPUT`

## pseudocode

```c

```
