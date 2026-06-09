# GsDriverEntry

- ea: `0x14000c010`
- end: `0x14000c03c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000c044`
- `0x14000c1b8`

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
0x14000c010  mov     [rsp+arg_0], rbx
0x14000c015  push    rdi
0x14000c016  sub     rsp, 20h
0x14000c01a  mov     rbx, rdx
0x14000c01d  mov     rdi, rcx
0x14000c020  call    __security_init_cookie
0x14000c025  mov     rdx, rbx; RegistryPath
0x14000c028  mov     rcx, rdi; DriverObject
0x14000c02b  call    DriverEntry
0x14000c030  mov     rbx, [rsp+28h+arg_0]
0x14000c035  add     rsp, 20h
0x14000c039  pop     rdi
0x14000c03a  retn
```
