# GsDriverEntry

- ea: `0x140040010`
- end: `0x14004003c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140040044`
- `0x140040078`

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
0x140040010  mov     [rsp+arg_0], rbx
0x140040015  push    rdi
0x140040016  sub     rsp, 20h
0x14004001a  mov     rbx, rdx
0x14004001d  mov     rdi, rcx
0x140040020  call    __security_init_cookie
0x140040025  mov     rdx, rbx; RegistryPath
0x140040028  mov     rcx, rdi; DriverObject
0x14004002b  call    DriverEntry
0x140040030  mov     rbx, [rsp+28h+arg_0]
0x140040035  add     rsp, 20h
0x140040039  pop     rdi
0x14004003a  retn
```
