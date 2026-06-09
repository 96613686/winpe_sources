# __security_check_cookie

- ea: `0x140007db0`
- end: `0x140007dce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `75`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000142c`
- `0x1400014f0`
- `0x140001564`
- `0x140001600`
- `0x1400016cc`
- `0x140001760`
- `0x1400017dc`
- `0x140001888`
- `0x140001950`
- `0x1400019b8`
- `0x140001a38`
- `0x140001b6c`
- `0x140001c70`
- `0x140001d10`
- `0x140002720`
- `0x140002b80`
- `0x140002c90`
- `0x140003050`
- `0x14000310c`
- `0x1400032c8`
- `0x1400033dc`
- `0x140003524`
- `0x140003604`
- `0x1400036ec`
- `0x140003be0`
- `0x140003fcc`
- `0x140004290`
- `0x140004b60`
- `0x140005510`
- `0x140005920`
- `0x1400061e0`
- `0x140006500`
- `0x140006618`
- `0x140006b94`
- `0x140006d54`
- `0x140006eb0`
- `0x140006ffc`
- `0x140007c7c`
- `0x140014208`
- `0x1400143b0`
- `0x140014760`
- `0x1400148cc`
- `0x140014ac0`
- `0x140014b74`
- `0x14001504c`
- `0x1400150ec`
- `0x1400152e0`
- `0x1400154c4`
- `0x1400155bc`

## callees

- `0x140006d00`
- `0x140007db0`

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
0x140007db0  cmp     rcx, cs:__security_cookie
0x140007db7  jnz     short ReportFailure
0x140007db9  rol     rcx, 10h
0x140007dbd  test    cx, 0FFFFh
0x140007dc2  jnz     short RestoreRcx
0x140007dc4  retn
0x140007dc5  ror     rcx, 10h; StackCookie
0x140007dc9  jmp     __report_gsfailure
```
