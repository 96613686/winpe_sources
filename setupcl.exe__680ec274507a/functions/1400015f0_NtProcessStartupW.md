# NtProcessStartupW

- ea: `0x1400015f0`
- end: `0x140001607`
- name: `NtProcessStartupW`
- size: `23`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140001190`
- `0x140001610`

## pseudocode

```c
NTSTATUS __stdcall __noreturn NtProcessStartupW(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  NtProcessStartupW_AfterSecurityCookieInitialized(DriverObject);
  JUMPOUT(0x140001606LL);
}

```

## disassembly

```asm
0x1400015f0  push    rbx
0x1400015f2  sub     rsp, 20h
0x1400015f6  mov     rbx, rcx
0x1400015f9  call    __security_init_cookie
0x1400015fe  mov     rcx, rbx
0x140001601  call    NtProcessStartupW_AfterSecurityCookieInitialized
```
