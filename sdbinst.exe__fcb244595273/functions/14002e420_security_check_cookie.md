# __security_check_cookie

- ea: `0x14002e420`
- end: `0x14002e43e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `88`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001214`
- `0x140002b4c`
- `0x140002de0`
- `0x140003410`
- `0x1400037e0`
- `0x1400038f0`
- `0x140003b60`
- `0x140003c88`
- `0x140003ff4`
- `0x140004324`
- `0x140004694`
- `0x1400046f4`
- `0x140004848`
- `0x140004c74`
- `0x140004df8`
- `0x140005668`
- `0x140005988`
- `0x140005b30`
- `0x140005b88`
- `0x140006238`
- `0x140006480`
- `0x140007308`
- `0x1400075a8`
- `0x14000792c`
- `0x1400083f0`
- `0x140008500`
- `0x140009b9c`
- `0x14000a058`
- `0x14000b574`
- `0x14000b83c`
- `0x14000c540`
- `0x14000f074`
- `0x14000f158`
- `0x14000f28c`
- `0x14000f5a8`
- `0x14000f644`
- `0x14001031c`
- `0x140010ae8`
- `0x1400115f8`
- `0x140012914`
- `0x140012be0`
- `0x140012db0`
- `0x140012ea0`
- `0x140013060`
- `0x1400131a0`
- `0x140013280`
- `0x1400133f0`
- `0x140015b08`
- `0x140015cbc`

## callees

- `0x140001cc0`
- `0x14002e420`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x14002e420  cmp     rcx, cs:__security_cookie
0x14002e427  jnz     short loc_14002E439
0x14002e429  rol     rcx, 10h
0x14002e42d  test    cx, 0FFFFh
0x14002e432  jnz     short loc_14002E435
0x14002e434  retn
0x14002e435  ror     rcx, 10h
0x14002e439  jmp     __report_gsfailure
```
