# __security_check_cookie

- ea: `0x180002230`
- end: `0x18000224e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800036bc`
- `0x180003958`
- `0x180003bd0`
- `0x180003f74`
- `0x1800044d4`
- `0x18000484c`
- `0x1800059f4`
- `0x180006730`
- `0x180006f54`
- `0x18000731c`
- `0x1800078fc`
- `0x180007ce8`
- `0x180007f18`
- `0x180007fc4`
- `0x180008108`
- `0x18000834c`
- `0x18000855c`
- `0x18000868c`
- `0x180008828`
- `0x1800089a8`
- `0x180008e4c`
- `0x180009650`

## callees

- `0x180002230`
- `0x1800027f0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180002230  cmp     rcx, cs:__security_cookie
0x180002237  jnz     short ReportFailure
0x180002239  rol     rcx, 10h
0x18000223d  test    cx, 0FFFFh
0x180002242  jnz     short RestoreRcx
0x180002244  retn
0x180002245  ror     rcx, 10h; StackCookie
0x180002249  jmp     __report_gsfailure
```
