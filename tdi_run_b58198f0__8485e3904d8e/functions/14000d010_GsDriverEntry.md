# GsDriverEntry

- ea: `0x14000d010`
- end: `0x14000d03c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004a00`
- `0x14000d044`

## pseudocode

```c
NTSTATUS __stdcall GsDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  ULONG v4; // r8d

  _security_init_cookie();
  return DriverEntry(DriverObject, RegistryPath, v4);
}

```

## disassembly

```asm
0x14000d010  mov     [rsp+arg_0], rbx
0x14000d015  push    rdi
0x14000d016  sub     rsp, 20h
0x14000d01a  mov     rbx, rdx
0x14000d01d  mov     rdi, rcx
0x14000d020  call    __security_init_cookie
0x14000d025  mov     rdx, rbx; ConnectionContext
0x14000d028  mov     rcx, rdi; TdiEventContext
0x14000d02b  call    DriverEntry
0x14000d030  mov     rbx, [rsp+28h+arg_0]
0x14000d035  add     rsp, 20h
0x14000d039  pop     rdi
0x14000d03a  retn
```
