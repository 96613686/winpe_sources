# GsDriverEntry

- ea: `0x140036010`
- end: `0x14003603c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140036044`
- `0x140036078`

## pseudocode

```c
NTSTATUS __stdcall GsDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  return DriverEntry(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x140036010  mov     [rsp+arg_0], rbx
0x140036015  push    rdi
0x140036016  sub     rsp, 20h
0x14003601a  mov     rbx, rdx
0x14003601d  mov     rdi, rcx
0x140036020  call    __security_init_cookie
0x140036025  mov     rdx, rbx; RegistryPath
0x140036028  mov     rcx, rdi; DriverObject
0x14003602b  call    DriverEntry
0x140036030  mov     rbx, [rsp+28h+arg_0]
0x140036035  add     rsp, 20h
0x140036039  pop     rdi
0x14003603a  retn
```
