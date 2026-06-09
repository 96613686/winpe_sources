# __security_check_cookie

- ea: `0x1800031b0`
- end: `0x1800031ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f80`
- `0x180002198`
- `0x1800025b8`
- `0x180002b00`
- `0x18000310c`

## callees

- `0x180001800`
- `0x1800031b0`

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
0x1800031b0  cmp     rcx, cs:__security_cookie
0x1800031b7  jnz     short ReportFailure
0x1800031b9  rol     rcx, 10h
0x1800031bd  test    cx, 0FFFFh
0x1800031c2  jnz     short RestoreRcx
0x1800031c4  retn
0x1800031c5  ror     rcx, 10h
0x1800031c9  jmp     __report_gsfailure
```
