# FxDriverEntry

- ea: `0x140010100`
- end: `0x14001012c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140010134`
- `0x14001e008`

## pseudocode

```c
NTSTATUS __stdcall FxDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  return FxDriverEntryWorker(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x140010100  mov     [rsp+arg_0], rbx
0x140010105  push    rdi
0x140010106  sub     rsp, 20h
0x14001010a  mov     rbx, rdx
0x14001010d  mov     rdi, rcx
0x140010110  call    __security_init_cookie
0x140010115  mov     rdx, rbx; RegistryPath
0x140010118  mov     rcx, rdi; DriverObject
0x14001011b  call    FxDriverEntryWorker
0x140010120  mov     rbx, [rsp+28h+arg_0]
0x140010125  add     rsp, 20h
0x140010129  pop     rdi
0x14001012a  retn
```
