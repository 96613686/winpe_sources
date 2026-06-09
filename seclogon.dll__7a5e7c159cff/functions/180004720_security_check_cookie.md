# __security_check_cookie

- ea: `0x180004720`
- end: `0x18000473e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001470`
- `0x180002110`
- `0x180004620`

## callees

- `0x1800039d0`
- `0x180004720`

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
0x180004720  cmp     rcx, cs:__security_cookie
0x180004727  jnz     short ReportFailure
0x180004729  rol     rcx, 10h
0x18000472d  test    cx, 0FFFFh
0x180004732  jnz     short RestoreRcx
0x180004734  retn
0x180004735  ror     rcx, 10h
0x180004739  jmp     __report_gsfailure
```
