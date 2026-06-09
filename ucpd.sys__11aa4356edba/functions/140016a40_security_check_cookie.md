# __security_check_cookie

- ea: `0x140016a40`
- end: `0x140016a5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `128`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010d0`
- `0x140001138`
- `0x1400013f0`
- `0x140001568`
- `0x14000189c`
- `0x140001b20`
- `0x140001c70`
- `0x140001dc0`
- `0x140001fa0`
- `0x1400022cc`
- `0x1400024b0`
- `0x140002af0`
- `0x140002cec`
- `0x1400032c4`
- `0x14000338c`
- `0x140003608`
- `0x140003778`
- `0x140003af8`
- `0x140003d7c`
- `0x140004868`
- `0x1400049cc`
- `0x140004e34`
- `0x140004fb0`
- `0x140005138`
- `0x140005268`
- `0x140005374`
- `0x1400055e0`
- `0x14000587c`
- `0x1400061b0`
- `0x1400062d4`
- `0x140006430`
- `0x14000651c`
- `0x140006724`
- `0x140006828`
- `0x1400069b0`
- `0x140006bf8`
- `0x140006ca4`
- `0x140006ef8`
- `0x140007178`
- `0x14000741c`
- `0x14000754c`
- `0x14000767c`
- `0x1400077f0`
- `0x140007b38`
- `0x140007e98`
- `0x1400082bc`
- `0x140008700`
- `0x140008d84`
- `0x140009390`

## callees

- `0x140015ff0`
- `0x140016a40`

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
0x140016a40  cmp     rcx, cs:__security_cookie
0x140016a47  jnz     short ReportFailure
0x140016a49  rol     rcx, 10h
0x140016a4d  test    cx, 0FFFFh
0x140016a52  jnz     short RestoreRcx
0x140016a54  retn
0x140016a55  ror     rcx, 10h; StackCookie
0x140016a59  jmp     __report_gsfailure
```
