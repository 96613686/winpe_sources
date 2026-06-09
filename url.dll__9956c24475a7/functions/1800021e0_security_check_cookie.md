# __security_check_cookie

- ea: `0x1800021e0`
- end: `0x1800021fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001a70`
- `0x180001c20`
- `0x180002138`

## callees

- `0x180001520`
- `0x1800021e0`

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
0x1800021e0  cmp     rcx, cs:__security_cookie
0x1800021e7  jnz     short ReportFailure
0x1800021e9  rol     rcx, 10h
0x1800021ed  test    cx, 0FFFFh
0x1800021f2  jnz     short RestoreRcx
0x1800021f4  retn
0x1800021f5  ror     rcx, 10h
0x1800021f9  jmp     __report_gsfailure
```
