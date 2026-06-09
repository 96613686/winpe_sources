# __security_check_cookie

- ea: `0x180003c30`
- end: `0x180003c4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x180002420`
- `0x180002780`
- `0x180003710`
- `0x180003b90`

## callees

- `0x180001790`
- `0x180003c30`

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
0x180003c30  cmp     rcx, cs:__security_cookie
0x180003c37  jnz     short ReportFailure
0x180003c39  rol     rcx, 10h
0x180003c3d  test    cx, 0FFFFh
0x180003c42  jnz     short RestoreRcx
0x180003c44  retn
0x180003c45  ror     rcx, 10h
0x180003c49  jmp     __report_gsfailure
```
