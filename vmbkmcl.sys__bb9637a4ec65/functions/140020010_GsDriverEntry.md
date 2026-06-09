# GsDriverEntry

- ea: `0x140020010`
- end: `0x14002003c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140020044`
- `0x1400202a8`

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
0x140020010  mov     [rsp+arg_0], rbx
0x140020015  push    rdi
0x140020016  sub     rsp, 20h
0x14002001a  mov     rbx, rdx
0x14002001d  mov     rdi, rcx
0x140020020  call    __security_init_cookie
0x140020025  mov     rdx, rbx; RegistryPath
0x140020028  mov     rcx, rdi; DriverObject
0x14002002b  call    DriverEntry
0x140020030  mov     rbx, [rsp+28h+arg_0]
0x140020035  add     rsp, 20h
0x140020039  pop     rdi
0x14002003a  retn
```
