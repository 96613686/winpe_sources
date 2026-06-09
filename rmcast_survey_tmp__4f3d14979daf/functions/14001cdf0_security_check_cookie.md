# __security_check_cookie

- ea: `0x14001cdf0`
- end: `0x14001ce0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400013b8`
- `0x14000813c`
- `0x14000a868`
- `0x14000ab60`
- `0x14000b0b0`
- `0x14000bf5c`
- `0x14000ec50`
- `0x14000f2d8`
- `0x140010ae4`
- `0x140012424`
- `0x140012efc`
- `0x140013d90`
- `0x140016a74`
- `0x1400185a4`
- `0x140018d80`
- `0x140019424`
- `0x14001ab38`
- `0x14001b8f8`
- `0x14001bcec`
- `0x14001cb5c`
- `0x140036a90`
- `0x140036b48`
- `0x140036d5c`
- `0x1400373f8`
- `0x140037ac4`
- `0x140037dd0`
- `0x140038784`
- `0x140038884`
- `0x140038afc`
- `0x14003a2fc`

## callees

- `0x140001010`
- `0x14001cdf0`

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
0x14001cdf0  cmp     rcx, cs:__security_cookie
0x14001cdf7  jnz     short ReportFailure
0x14001cdf9  rol     rcx, 10h
0x14001cdfd  test    cx, 0FFFFh
0x14001ce02  jnz     short RestoreRcx
0x14001ce04  retn
0x14001ce05  ror     rcx, 10h; StackCookie
0x14001ce09  jmp     __report_gsfailure
```
