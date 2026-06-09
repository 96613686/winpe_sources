# FxDriverEntry

- ea: `0x14000a430`
- end: `0x14000a45c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000a464`
- `0x140013008`

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
0x14000a430  mov     [rsp+arg_0], rbx
0x14000a435  push    rdi
0x14000a436  sub     rsp, 20h
0x14000a43a  mov     rbx, rdx
0x14000a43d  mov     rdi, rcx
0x14000a440  call    __security_init_cookie
0x14000a445  mov     rdx, rbx; RegistryPath
0x14000a448  mov     rcx, rdi; DriverObject
0x14000a44b  call    FxDriverEntryWorker
0x14000a450  mov     rbx, [rsp+28h+arg_0]
0x14000a455  add     rsp, 20h
0x14000a459  pop     rdi
0x14000a45a  retn
```
