# __security_check_cookie

- ea: `0x18000ba60`
- end: `0x18000ba7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003178`
- `0x18000908c`
- `0x18000a72c`
- `0x18000aaa0`
- `0x18000aea4`
- `0x18000b960`

## callees

- `0x180001d20`
- `0x18000ba60`

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
0x18000ba60  cmp     rcx, cs:__security_cookie
0x18000ba67  jnz     short ReportFailure
0x18000ba69  rol     rcx, 10h
0x18000ba6d  test    cx, 0FFFFh
0x18000ba72  jnz     short RestoreRcx
0x18000ba74  retn
0x18000ba75  ror     rcx, 10h
0x18000ba79  jmp     __report_gsfailure
```
