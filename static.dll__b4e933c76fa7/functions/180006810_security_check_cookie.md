# __security_check_cookie

- ea: `0x180006810`
- end: `0x18000682e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002dd8`
- `0x180003d74`
- `0x180004704`
- `0x1800059bc`
- `0x18000675c`

## callees

- `0x180001ae0`
- `0x180006810`

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
0x180006810  cmp     rcx, cs:__security_cookie
0x180006817  jnz     short ReportFailure
0x180006819  rol     rcx, 10h
0x18000681d  test    cx, 0FFFFh
0x180006822  jnz     short RestoreRcx
0x180006824  retn
0x180006825  ror     rcx, 10h
0x180006829  jmp     __report_gsfailure
```
