# __security_check_cookie

- ea: `0x180002980`
- end: `0x18000299e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001300`
- `0x180001fb0`
- `0x180002300`
- `0x180003318`

## callees

- `0x180002980`
- `0x180002eb0`

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
0x180002980  cmp     rcx, cs:__security_cookie
0x180002987  jnz     short ReportFailure
0x180002989  rol     rcx, 10h
0x18000298d  test    cx, 0FFFFh
0x180002992  jnz     short RestoreRcx
0x180002994  retn
0x180002995  ror     rcx, 10h; StackCookie
0x180002999  jmp     __report_gsfailure
```
