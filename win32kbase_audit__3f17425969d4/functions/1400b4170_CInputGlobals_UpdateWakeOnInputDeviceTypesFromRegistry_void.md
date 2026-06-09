# CInputGlobals::UpdateWakeOnInputDeviceTypesFromRegistry(void)

- ea: `0x1400b4170`
- end: `0x1400b4396`
- name: `?UpdateWakeOnInputDeviceTypesFromRegistry@CInputGlobals@@QEAAXXZ`
- size: `550`
- prototype: `void __fastcall(CInputGlobals *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x140179104`

## callees

- `0x14000b9f0`
- `0x14000c490`
- `0x1400b352c`
- `0x1400b4170`
- `0x1402388e0`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400b4214`
- `ntoskrnl!ZwOpenKey` at `0x1400b4214`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b426c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b433a`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b426c`
- `ntoskrnl!ZwQueryValueKey` at `0x1400b433a`
- `ntoskrnl!ZwClose` at `0x1400b4280`
- `ntoskrnl!ZwClose` at `0x1400b4385`
- `ntoskrnl!ZwClose` at `0x1400b4280`
- `ntoskrnl!ZwClose` at `0x1400b4385`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b41d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b423d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b430b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b41d3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b423d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400b430b`

## string_xrefs

- `0x1400b41b8`: `\Registry\Machine\SYSTEM\INPUT`

## pseudocode

```c

```
