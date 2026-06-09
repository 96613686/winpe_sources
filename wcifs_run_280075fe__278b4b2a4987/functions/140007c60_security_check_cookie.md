# __security_check_cookie

- ea: `0x140007c60`
- end: `0x140007c7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010d4`
- `0x140001710`
- `0x140002be4`
- `0x14000308c`
- `0x140003274`
- `0x1400033a0`
- `0x140003930`
- `0x140006160`
- `0x14000672c`
- `0x14000678c`
- `0x140006fd8`
- `0x140007484`
- `0x140007bdc`
- `0x140014c90`
- `0x1400184f0`
- `0x14001939c`
- `0x140019c40`
- `0x140019da0`
- `0x14001a20c`
- `0x14001b0bc`
- `0x14001b524`
- `0x14001c244`
- `0x14001c688`
- `0x14001d8dc`
- `0x14001e028`
- `0x14001f1c8`
- `0x14001fe40`
- `0x140020840`
- `0x140022154`
- `0x140022820`
- `0x140022f90`
- `0x140023644`
- `0x1400241c4`
- `0x140026210`
- `0x140026b58`
- `0x140026de0`
- `0x140027854`
- `0x140027f24`
- `0x140028a80`
- `0x140029608`
- `0x14002a0cc`
- `0x14002a614`
- `0x14002ac00`
- `0x14002ad04`
- `0x14002d5f8`
- `0x14002da54`
- `0x14002ea5c`
- `0x14002ee78`
- `0x14002fb20`
- `0x14003027c`

## callees

- `0x140004020`
- `0x140007c60`

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
0x140007c60  cmp     rcx, cs:__security_cookie
0x140007c67  jnz     short ReportFailure
0x140007c69  rol     rcx, 10h
0x140007c6d  test    cx, 0FFFFh
0x140007c72  jnz     short RestoreRcx
0x140007c74  retn
0x140007c75  ror     rcx, 10h; StackCookie
0x140007c79  jmp     __report_gsfailure
```
