# __security_check_cookie

- ea: `0x180001670`
- end: `0x18000168e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002578`
- `0x180002708`
- `0x180002794`
- `0x180002820`
- `0x18000317c`
- `0x180003418`
- `0x180003e4c`
- `0x1800041f0`
- `0x180004830`
- `0x180005354`
- `0x1800056cc`
- `0x1800067b8`
- `0x180006a34`
- `0x180006b40`
- `0x1800074e8`
- `0x180008434`
- `0x180008e74`
- `0x1800090b4`
- `0x18000af30`
- `0x18000b0c8`
- `0x18000db2c`

## callees

- `0x180001670`
- `0x180001c00`

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
0x180001670  cmp     rcx, cs:__security_cookie
0x180001677  jnz     short ReportFailure
0x180001679  rol     rcx, 10h
0x18000167d  test    cx, 0FFFFh
0x180001682  jnz     short RestoreRcx
0x180001684  retn
0x180001685  ror     rcx, 10h; StackCookie
0x180001689  jmp     __report_gsfailure
```
