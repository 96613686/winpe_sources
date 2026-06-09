# GsDriverEntry

- ea: `0x180056010`
- end: `0x18005603c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180011080`
- `0x180056044`

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
0x180056010  mov     [rsp+arg_0], rbx
0x180056015  push    rdi
0x180056016  sub     rsp, 20h
0x18005601a  mov     rbx, rdx
0x18005601d  mov     rdi, rcx
0x180056020  call    __security_init_cookie
0x180056025  mov     rdx, rbx; RegistryPath
0x180056028  mov     rcx, rdi; DriverObject
0x18005602b  call    DriverEntry
0x180056030  mov     rbx, [rsp+28h+arg_0]
0x180056035  add     rsp, 20h
0x180056039  pop     rdi
0x18005603a  retn
```
