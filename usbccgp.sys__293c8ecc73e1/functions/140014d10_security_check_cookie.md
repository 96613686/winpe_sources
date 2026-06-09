# __security_check_cookie

- ea: `0x140014d10`
- end: `0x140014d2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a938`
- `0x14000c7e8`
- `0x14000d9b4`
- `0x14001109c`
- `0x140011a78`
- `0x14001268c`
- `0x140014bdc`
- `0x140022de0`
- `0x1400235d0`
- `0x140025bd0`
- `0x140025f38`
- `0x14002610c`
- `0x14002a82c`
- `0x14002befc`
- `0x14002c2cc`
- `0x14002d27c`
- `0x14002dab0`
- `0x14002db28`
- `0x14002f328`

## callees

- `0x140010f50`
- `0x140014d10`

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
0x140014d10  cmp     rcx, cs:__security_cookie
0x140014d17  jnz     short ReportFailure
0x140014d19  rol     rcx, 10h
0x140014d1d  test    cx, 0FFFFh
0x140014d22  jnz     short RestoreRcx
0x140014d24  retn
0x140014d25  ror     rcx, 10h; StackCookie
0x140014d29  jmp     __report_gsfailure
```
