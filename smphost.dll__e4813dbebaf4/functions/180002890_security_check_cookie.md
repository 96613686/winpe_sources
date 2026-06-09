# __security_check_cookie

- ea: `0x180002890`
- end: `0x1800028ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010b0`
- `0x180001bb8`
- `0x180001fec`
- `0x180002300`
- `0x180002460`
- `0x1800027f8`

## callees

- `0x1800019f0`
- `0x180002890`

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
0x180002890  cmp     rcx, cs:__security_cookie
0x180002897  jnz     short ReportFailure
0x180002899  rol     rcx, 10h
0x18000289d  test    cx, 0FFFFh
0x1800028a2  jnz     short RestoreRcx
0x1800028a4  retn
0x1800028a5  ror     rcx, 10h
0x1800028a9  jmp     __report_gsfailure
```
