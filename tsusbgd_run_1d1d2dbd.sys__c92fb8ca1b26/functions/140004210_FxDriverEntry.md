# FxDriverEntry

- ea: `0x140004210`
- end: `0x14000423c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140004244`
- `0x14000d008`

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
0x140004210  mov     [rsp+arg_0], rbx
0x140004215  push    rdi
0x140004216  sub     rsp, 20h
0x14000421a  mov     rbx, rdx
0x14000421d  mov     rdi, rcx
0x140004220  call    __security_init_cookie
0x140004225  mov     rdx, rbx; RegistryPath
0x140004228  mov     rcx, rdi; DriverObject
0x14000422b  call    FxDriverEntryWorker
0x140004230  mov     rbx, [rsp+28h+arg_0]
0x140004235  add     rsp, 20h
0x140004239  pop     rdi
0x14000423a  retn
```
