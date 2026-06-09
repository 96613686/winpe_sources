# DriverEntry

- ea: `0x140004a00`
- end: `0x140004a03`
- name: `DriverEntry`
- size: `3`
- prototype: `NTSTATUS __stdcall(PVOID TdiEventContext, PVOID ConnectionContext, ULONG BytesAvailable)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x14000d010`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(PVOID TdiEventContext, PVOID ConnectionContext, ULONG BytesAvailable)
{
  return 0;
}

```

## disassembly

```asm
0x140004a00  xor     eax, eax; TdiDefaultDisconnectHandler
0x140004a02  retn
```
