# __security_check_cookie

- ea: `0x140039740`
- end: `0x14003975e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `109`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001148`
- `0x140001214`
- `0x1400012c0`
- `0x140001374`
- `0x140001424`
- `0x1400014a0`
- `0x14000153c`
- `0x1400034a8`
- `0x1400038e0`
- `0x14000660c`
- `0x140006838`
- `0x140006b70`
- `0x140006fac`
- `0x1400072cc`
- `0x140007b5c`
- `0x140007c90`
- `0x140008278`
- `0x140008758`
- `0x1400092bc`
- `0x14000a4f0`
- `0x14000b0a8`
- `0x14000bf68`
- `0x14000f63c`
- `0x140010540`
- `0x1400110f0`
- `0x1400116fc`
- `0x1400120d0`
- `0x140012568`
- `0x140013964`
- `0x140013bf0`
- `0x140013da0`
- `0x140014a34`
- `0x140015214`
- `0x1400157a0`
- `0x140015a00`
- `0x140015b10`
- `0x140016228`
- `0x140016358`
- `0x1400171d0`
- `0x1400179c4`
- `0x140019874`
- `0x1400199e4`
- `0x14001b1ac`
- `0x14001b220`
- `0x14001b464`
- `0x14001b5b4`
- `0x14001ba78`
- `0x14001c0e8`
- `0x14001c1ac`

## callees

- `0x14001ac50`
- `0x140039740`

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
0x140039740  cmp     rcx, cs:__security_cookie
0x140039747  jnz     short ReportFailure
0x140039749  rol     rcx, 10h
0x14003974d  test    cx, 0FFFFh
0x140039752  jnz     short RestoreRcx
0x140039754  retn
0x140039755  ror     rcx, 10h; StackCookie
0x140039759  jmp     __report_gsfailure
```
