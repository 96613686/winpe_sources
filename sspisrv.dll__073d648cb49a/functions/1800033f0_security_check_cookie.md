# __security_check_cookie

- ea: `0x1800033f0`
- end: `0x18000340e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001470`
- `0x180001540`
- `0x1800016d0`
- `0x180001ac0`
- `0x180001c10`
- `0x18000235c`
- `0x180002740`
- `0x180002b70`
- `0x180002e10`
- `0x180003060`
- `0x180003180`
- `0x180003220`
- `0x1800032f4`

## callees

- `0x180002160`
- `0x1800033f0`

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
0x1800033f0  cmp     rcx, cs:__security_cookie
0x1800033f7  jnz     short ReportFailure
0x1800033f9  rol     rcx, 10h
0x1800033fd  test    cx, 0FFFFh
0x180003402  jnz     short RestoreRcx
0x180003404  retn
0x180003405  ror     rcx, 10h
0x180003409  jmp     __report_gsfailure
```
