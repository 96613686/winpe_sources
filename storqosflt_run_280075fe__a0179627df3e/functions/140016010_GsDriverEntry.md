# GsDriverEntry

- ea: `0x140016010`
- end: `0x14001603c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140016044`
- `0x1400161ec`

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
0x140016010  mov     [rsp+arg_0], rbx
0x140016015  push    rdi
0x140016016  sub     rsp, 20h
0x14001601a  mov     rbx, rdx
0x14001601d  mov     rdi, rcx
0x140016020  call    __security_init_cookie
0x140016025  mov     rdx, rbx; RegistryPath
0x140016028  mov     rcx, rdi; DriverObject
0x14001602b  call    DriverEntry
0x140016030  mov     rbx, [rsp+28h+arg_0]
0x140016035  add     rsp, 20h
0x140016039  pop     rdi
0x14001603a  retn
```
