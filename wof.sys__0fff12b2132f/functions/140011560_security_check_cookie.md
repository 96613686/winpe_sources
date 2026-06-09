# __security_check_cookie

- ea: `0x140011560`
- end: `0x14001157e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `56`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140002b50`
- `0x140002fcc`
- `0x1400059a4`
- `0x140005e1c`
- `0x140006080`
- `0x1400075c0`
- `0x140008d30`
- `0x140009910`
- `0x14000a35c`
- `0x14000ac54`
- `0x14000ae04`
- `0x14000b1e8`
- `0x14000b4a4`
- `0x14000d470`
- `0x14000f2e4`
- `0x14000f4f8`
- `0x14000f970`
- `0x140010954`
- `0x140010f74`
- `0x14001145c`
- `0x140022048`
- `0x140023ec4`
- `0x140025ba0`
- `0x140026310`
- `0x1400263f0`
- `0x140027820`
- `0x140027fac`
- `0x1400288d4`
- `0x140028ef4`
- `0x140029c50`
- `0x140029d60`
- `0x140029e4c`
- `0x140029f28`
- `0x14002a040`
- `0x14002a700`
- `0x14002aa38`
- `0x14002c53c`
- `0x14002d940`
- `0x14002dcc0`
- `0x14002dfb8`
- `0x14002e1f4`
- `0x14002e578`
- `0x14002ea50`
- `0x140031330`
- `0x140032e94`
- `0x140033180`
- `0x1400350c8`
- `0x140036904`
- `0x140039a50`

## callees

- `0x14000da00`
- `0x140011560`

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
0x140011560  cmp     rcx, cs:__security_cookie
0x140011567  jnz     short ReportFailure
0x140011569  rol     rcx, 10h
0x14001156d  test    cx, 0FFFFh
0x140011572  jnz     short RestoreRcx
0x140011574  retn
0x140011575  ror     rcx, 10h; StackCookie
0x140011579  jmp     __report_gsfailure
```
