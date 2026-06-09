# __security_check_cookie

- ea: `0x1400184b0`
- end: `0x1400184ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001550`
- `0x140002ccc`
- `0x140003c9c`
- `0x140007b90`
- `0x14000a1b0`
- `0x14000aad0`
- `0x14000cb10`
- `0x14000cfc0`
- `0x14000d790`
- `0x14000db08`
- `0x14000e630`
- `0x14000eba0`
- `0x140010100`
- `0x1400119d0`
- `0x140011cb4`
- `0x140013174`
- `0x1400146c0`
- `0x140014988`
- `0x1400157cc`
- `0x1400159f0`
- `0x14001606c`
- `0x140016fec`
- `0x1400183bc`
- `0x1400233f0`
- `0x140024138`

## callees

- `0x1400121b0`
- `0x1400184b0`

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
0x1400184b0  cmp     rcx, cs:__security_cookie
0x1400184b7  jnz     short ReportFailure
0x1400184b9  rol     rcx, 10h
0x1400184bd  test    cx, 0FFFFh
0x1400184c2  jnz     short RestoreRcx
0x1400184c4  retn
0x1400184c5  ror     rcx, 10h; StackCookie
0x1400184c9  jmp     __report_gsfailure
```
