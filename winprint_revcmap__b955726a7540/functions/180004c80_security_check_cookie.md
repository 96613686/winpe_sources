# __security_check_cookie

- ea: `0x180004c80`
- end: `0x180004c9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800017d0`
- `0x180001d60`
- `0x180002400`
- `0x180003d80`
- `0x180005abc`
- `0x1800076d0`

## callees

- `0x180004c80`
- `0x1800051b0`

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
0x180004c80  cmp     rcx, cs:__security_cookie
0x180004c87  jnz     short ReportFailure
0x180004c89  rol     rcx, 10h
0x180004c8d  test    cx, 0FFFFh
0x180004c92  jnz     short RestoreRcx
0x180004c94  retn
0x180004c95  ror     rcx, 10h; StackCookie
0x180004c99  jmp     __report_gsfailure
```
