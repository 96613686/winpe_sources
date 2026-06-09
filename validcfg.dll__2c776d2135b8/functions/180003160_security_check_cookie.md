# __security_check_cookie

- ea: `0x180003160`
- end: `0x18000317e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800030bc`

## callees

- `0x180001f60`
- `0x180003160`

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
0x180003160  cmp     rcx, cs:__security_cookie
0x180003167  jnz     short ReportFailure
0x180003169  rol     rcx, 10h
0x18000316d  test    cx, 0FFFFh
0x180003172  jnz     short RestoreRcx
0x180003174  retn
0x180003175  ror     rcx, 10h
0x180003179  jmp     __report_gsfailure
```
