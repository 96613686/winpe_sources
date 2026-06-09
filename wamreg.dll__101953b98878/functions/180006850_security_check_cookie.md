# __security_check_cookie

- ea: `0x180006850`
- end: `0x18000686e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002850`
- `0x180002e7c`
- `0x180002f9c`
- `0x1800030b0`
- `0x180003d80`
- `0x1800041d4`
- `0x180004948`
- `0x180004acc`
- `0x180004dac`
- `0x180005138`
- `0x1800053d8`
- `0x180005584`
- `0x1800058a0`
- `0x1800066a4`
- `0x1800067a0`

## callees

- `0x1800015a0`
- `0x180006850`

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
0x180006850  cmp     rcx, cs:__security_cookie
0x180006857  jnz     short ReportFailure
0x180006859  rol     rcx, 10h
0x18000685d  test    cx, 0FFFFh
0x180006862  jnz     short RestoreRcx
0x180006864  retn
0x180006865  ror     rcx, 10h
0x180006869  jmp     __report_gsfailure
```
