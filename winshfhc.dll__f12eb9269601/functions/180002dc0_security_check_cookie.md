# __security_check_cookie

- ea: `0x180002dc0`
- end: `0x180002dde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002688`
- `0x180002d30`

## callees

- `0x180001780`
- `0x180002dc0`

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
0x180002dc0  cmp     rcx, cs:__security_cookie
0x180002dc7  jnz     short ReportFailure
0x180002dc9  rol     rcx, 10h
0x180002dcd  test    cx, 0FFFFh
0x180002dd2  jnz     short RestoreRcx
0x180002dd4  retn
0x180002dd5  ror     rcx, 10h
0x180002dd9  jmp     __report_gsfailure
```
