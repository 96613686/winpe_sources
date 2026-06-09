# NtProcessStartupW

- ea: `0x140003370`
- end: `0x140003387`
- name: `NtProcessStartupW`
- size: `23`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001190`
- `0x140003390`

## pseudocode

```c
NTSTATUS __stdcall __noreturn NtProcessStartupW(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  NtProcessStartupW_AfterSecurityCookieInitialized(DriverObject);
  JUMPOUT(0x140003386LL);
}

```

## disassembly

```asm
0x140003370  push    rbx
0x140003372  sub     rsp, 20h
0x140003376  mov     rbx, rcx
0x140003379  call    __security_init_cookie
0x14000337e  mov     rcx, rbx
0x140003381  call    NtProcessStartupW_AfterSecurityCookieInitialized
```
