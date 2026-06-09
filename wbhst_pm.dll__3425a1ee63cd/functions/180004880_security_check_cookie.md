# __security_check_cookie

- ea: `0x180004880`
- end: `0x18000489e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001bf8`
- `0x180002440`
- `0x180002670`
- `0x1800038f0`
- `0x180003b80`
- `0x180003fa0`
- `0x1800043c8`
- `0x1800045fc`
- `0x1800047c4`

## callees

- `0x180001790`
- `0x180004880`

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
0x180004880  cmp     rcx, cs:__security_cookie
0x180004887  jnz     short ReportFailure
0x180004889  rol     rcx, 10h
0x18000488d  test    cx, 0FFFFh
0x180004892  jnz     short RestoreRcx
0x180004894  retn
0x180004895  ror     rcx, 10h
0x180004899  jmp     __report_gsfailure
```
