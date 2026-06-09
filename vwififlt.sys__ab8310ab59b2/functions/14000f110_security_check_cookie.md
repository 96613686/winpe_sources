# __security_check_cookie

- ea: `0x14000f110`
- end: `0x14000f12e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002c90`
- `0x140003354`
- `0x1400033f0`
- `0x140003634`
- `0x140003b7c`
- `0x140004c50`
- `0x140004d70`
- `0x140005858`
- `0x140005bf0`
- `0x14000745c`
- `0x140007d58`
- `0x1400080f0`
- `0x14000aef0`
- `0x14000bfb8`
- `0x14000ca14`
- `0x14000efdc`

## callees

- `0x14000cea0`
- `0x14000f110`

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
0x14000f110  cmp     rcx, cs:__security_cookie
0x14000f117  jnz     short ReportFailure
0x14000f119  rol     rcx, 10h
0x14000f11d  test    cx, 0FFFFh
0x14000f122  jnz     short RestoreRcx
0x14000f124  retn
0x14000f125  ror     rcx, 10h; StackCookie
0x14000f129  jmp     __report_gsfailure
```
