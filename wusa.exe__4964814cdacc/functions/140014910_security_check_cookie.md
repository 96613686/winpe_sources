# __security_check_cookie

- ea: `0x140014910`
- end: `0x14001492e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `43`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400021b0`
- `0x140002444`
- `0x1400026bc`
- `0x140002a8c`
- `0x1400030b4`
- `0x14000342c`
- `0x14000456c`
- `0x14000539c`
- `0x140005c70`
- `0x140006fb8`
- `0x1400075b0`
- `0x1400087e4`
- `0x140008be0`
- `0x140009284`
- `0x140009390`
- `0x140009cd8`
- `0x14000afc0`
- `0x14000b84c`
- `0x14000c248`
- `0x14000c488`
- `0x14000c9ec`
- `0x14000d25c`
- `0x14000d44c`
- `0x14000d620`
- `0x14000db50`
- `0x14000e4c4`
- `0x14000e9ac`
- `0x14000f45c`
- `0x140010800`
- `0x14001181c`
- `0x140011dcc`
- `0x1400121f0`
- `0x140012b00`
- `0x140013020`
- `0x1400131a8`
- `0x14001327c`
- `0x14001331c`
- `0x1400133f0`
- `0x140013490`
- `0x1400135a4`
- `0x140013844`
- `0x140013a90`
- `0x1400147f4`

## callees

- `0x140001ab0`
- `0x140014910`

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
0x140014910  cmp     rcx, cs:__security_cookie
0x140014917  jnz     short loc_140014929
0x140014919  rol     rcx, 10h
0x14001491d  test    cx, 0FFFFh
0x140014922  jnz     short loc_140014925
0x140014924  retn
0x140014925  ror     rcx, 10h
0x140014929  jmp     __report_gsfailure
```
