# __security_check_cookie

- ea: `0x18002ffd0`
- end: `0x18002ffee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `187`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000109c`
- `0x180001158`
- `0x18000140c`
- `0x1800014c8`
- `0x18000565c`
- `0x180005770`
- `0x180005bec`
- `0x180005db0`
- `0x180005fc4`
- `0x1800063ec`
- `0x180006d3c`
- `0x18000728c`
- `0x1800078f0`
- `0x1800079ac`
- `0x180007aac`
- `0x180007ee0`
- `0x18000862c`
- `0x1800087c8`
- `0x1800089b4`
- `0x1800090a8`
- `0x180009168`
- `0x1800091d4`
- `0x1800096e0`
- `0x18000a0f0`
- `0x18000ab50`
- `0x18000acc4`
- `0x18000b6f0`
- `0x18000be28`
- `0x18000bf50`
- `0x18000c208`
- `0x18000c628`
- `0x18000cf60`
- `0x18000cfc0`
- `0x18000d1f0`
- `0x18000d590`
- `0x18000e0dc`
- `0x18000f8a8`
- `0x18000f9fc`
- `0x1800101b0`
- `0x180010738`
- `0x180010c1c`
- `0x180011484`
- `0x1800116a0`
- `0x1800118d4`
- `0x180011b2c`
- `0x180011d90`
- `0x180011e8c`
- `0x180011f80`
- `0x18001203c`
- `0x180012138`

## callees

- `0x18002ffd0`
- `0x1800300a0`

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
0x18002ffd0  cmp     rcx, cs:__security_cookie
0x18002ffd7  jnz     short ReportFailure
0x18002ffd9  rol     rcx, 10h
0x18002ffdd  test    cx, 0FFFFh
0x18002ffe2  jnz     short RestoreRcx
0x18002ffe4  retn
0x18002ffe5  ror     rcx, 10h
0x18002ffe9  jmp     __report_gsfailure
```
