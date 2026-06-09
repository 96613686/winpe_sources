# __security_check_cookie

- ea: `0x140009c50`
- end: `0x140009c6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001620`
- `0x140004b90`
- `0x140005470`
- `0x140005660`
- `0x140005dcc`
- `0x140006450`
- `0x140006618`
- `0x140006ce4`
- `0x140007310`
- `0x140008ca8`
- `0x140009268`
- `0x140009b0c`
- `0x14000b380`
- `0x14001b010`
- `0x14001ba40`
- `0x14001bc5c`
- `0x14001be40`
- `0x14001cd10`
- `0x14001ce40`
- `0x14001d080`
- `0x14001d150`
- `0x14001d4e4`
- `0x14001d65c`
- `0x14001e11c`
- `0x14001e4a0`
- `0x14001e770`
- `0x14001e7e4`
- `0x14001ea54`
- `0x14001ed50`
- `0x14001f2d0`
- `0x1400202cc`
- `0x1400204a4`
- `0x1400207f4`
- `0x140021680`
- `0x1400226bc`
- `0x140022920`
- `0x140023038`
- `0x140023350`
- `0x140023654`
- `0x140023c90`
- `0x140023d00`
- `0x140023d88`
- `0x140025f30`
- `0x14002a080`
- `0x14002a678`
- `0x14002a804`

## callees

- `0x140004b60`
- `0x140009c50`

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
0x140009c50  cmp     rcx, cs:__security_cookie
0x140009c57  jnz     short ReportFailure
0x140009c59  rol     rcx, 10h
0x140009c5d  test    cx, 0FFFFh
0x140009c62  jnz     short RestoreRcx
0x140009c64  retn
0x140009c65  ror     rcx, 10h; StackCookie
0x140009c69  jmp     __report_gsfailure
```
