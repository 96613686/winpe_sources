# NtProcessStartupW

- ea: `0x140005be0`
- end: `0x140005bf7`
- name: `NtProcessStartupW`
- size: `23`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140005c00`
- `0x14000eeb0`

## pseudocode

```c
NTSTATUS __stdcall __noreturn NtProcessStartupW(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  NtProcessStartupW_AfterSecurityCookieInitialized((__int64)DriverObject);
  JUMPOUT(0x140005BF6LL);
}

```

## disassembly

```asm
0x140005be0  push    rbx
0x140005be2  sub     rsp, 20h
0x140005be6  mov     rbx, rcx
0x140005be9  call    __security_init_cookie
0x140005bee  mov     rcx, rbx
0x140005bf1  call    NtProcessStartupW_AfterSecurityCookieInitialized
```
