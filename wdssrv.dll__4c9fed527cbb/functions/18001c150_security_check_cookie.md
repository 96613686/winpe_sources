# __security_check_cookie

- ea: `0x18001c150`
- end: `0x18001c16e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006b48`
- `0x180006df8`
- `0x18000794c`
- `0x180007d44`
- `0x180008288`
- `0x180008c58`
- `0x1800091d4`
- `0x180009560`
- `0x180009da4`
- `0x18000aa50`
- `0x18000ae68`
- `0x18000b4e4`
- `0x18000b5f4`
- `0x18000c004`
- `0x18000d380`
- `0x18000dec0`
- `0x18000eee8`
- `0x18000f338`
- `0x18000fda8`
- `0x180013af8`
- `0x180014850`
- `0x180014c24`
- `0x180015144`
- `0x180015c50`
- `0x180015f1c`
- `0x1800162d4`
- `0x180016b08`
- `0x180016f98`
- `0x180017c5c`
- `0x180017f24`
- `0x1800183b0`
- `0x1800184d0`
- `0x1800186f0`
- `0x180018cdc`
- `0x180019d14`
- `0x18001c098`

## callees

- `0x180001ca0`
- `0x18001c150`

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
0x18001c150  cmp     rcx, cs:__security_cookie
0x18001c157  jnz     short ReportFailure
0x18001c159  rol     rcx, 10h
0x18001c15d  test    cx, 0FFFFh
0x18001c162  jnz     short RestoreRcx
0x18001c164  retn
0x18001c165  ror     rcx, 10h
0x18001c169  jmp     __report_gsfailure
```
