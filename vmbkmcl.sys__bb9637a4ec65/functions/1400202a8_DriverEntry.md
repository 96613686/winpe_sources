# DriverEntry

- ea: `0x1400202a8`
- end: `0x1400202ae`
- name: `DriverEntry`
- size: `6`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140020010`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  return -1073741823;
}

```

## disassembly

```asm
0x1400202a8  mov     eax, 0C0000001h
0x1400202ad  retn
```
