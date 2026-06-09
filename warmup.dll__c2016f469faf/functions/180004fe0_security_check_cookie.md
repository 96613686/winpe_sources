# __security_check_cookie

- ea: `0x180004fe0`
- end: `0x180004ffe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003818`
- `0x180003c74`
- `0x180004204`
- `0x180004480`
- `0x180004bc0`
- `0x180004f48`

## callees

- `0x180001780`
- `0x180004fe0`

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
0x180004fe0  cmp     rcx, cs:__security_cookie
0x180004fe7  jnz     short ReportFailure
0x180004fe9  rol     rcx, 10h
0x180004fed  test    cx, 0FFFFh
0x180004ff2  jnz     short RestoreRcx
0x180004ff4  retn
0x180004ff5  ror     rcx, 10h
0x180004ff9  jmp     __report_gsfailure
```
