# __security_check_cookie

- ea: `0x1800036c0`
- end: `0x1800036de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002460`
- `0x180002dec`
- `0x180003060`
- `0x180003298`
- `0x180003620`

## callees

- `0x180001700`
- `0x1800036c0`

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
0x1800036c0  cmp     rcx, cs:__security_cookie
0x1800036c7  jnz     short ReportFailure
0x1800036c9  rol     rcx, 10h
0x1800036cd  test    cx, 0FFFFh
0x1800036d2  jnz     short RestoreRcx
0x1800036d4  retn
0x1800036d5  ror     rcx, 10h
0x1800036d9  jmp     __report_gsfailure
```
