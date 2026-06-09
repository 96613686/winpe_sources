# DriverEntry

- ea: `0x140024b18`
- end: `0x140024b1e`
- name: `DriverEntry`
- size: `6`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140024010`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  return -1073741823;
}

```

## disassembly

```asm
0x140024b18  mov     eax, 0C0000001h
0x140024b1d  retn
```
