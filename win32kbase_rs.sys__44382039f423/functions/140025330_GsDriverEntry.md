# GsDriverEntry

- ea: `0x140025330`
- end: `0x14002535c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400252f4`
- `0x140025364`

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
0x140025330  mov     [rsp+arg_0], rbx
0x140025335  push    rdi
0x140025336  sub     rsp, 20h
0x14002533a  mov     rbx, rdx
0x14002533d  mov     rdi, rcx
0x140025340  call    __security_init_cookie
0x140025345  mov     rdx, rbx; RegistryPath
0x140025348  mov     rcx, rdi; DriverObject
0x14002534b  call    DriverEntry
0x140025350  mov     rbx, [rsp+28h+arg_0]
0x140025355  add     rsp, 20h
0x140025359  pop     rdi
0x14002535a  retn
```
