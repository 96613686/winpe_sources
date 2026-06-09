# FxDriverEntry

- ea: `0x14000bf40`
- end: `0x14000bf6c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000bf74`
- `0x140030008`

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
0x14000bf40  mov     [rsp+arg_0], rbx
0x14000bf45  push    rdi
0x14000bf46  sub     rsp, 20h
0x14000bf4a  mov     rbx, rdx
0x14000bf4d  mov     rdi, rcx
0x14000bf50  call    __security_init_cookie
0x14000bf55  mov     rdx, rbx; RegistryPath
0x14000bf58  mov     rcx, rdi; DriverObject
0x14000bf5b  call    FxDriverEntryWorker
0x14000bf60  mov     rbx, [rsp+28h+arg_0]
0x14000bf65  add     rsp, 20h
0x14000bf69  pop     rdi
0x14000bf6a  retn
```
