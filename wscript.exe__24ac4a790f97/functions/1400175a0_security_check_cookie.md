# __security_check_cookie

- ea: `0x1400175a0`
- end: `0x1400175be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003464`
- `0x140003700`
- `0x1400038f0`
- `0x140003cc0`
- `0x140003fdc`
- `0x140004ee8`
- `0x140006004`
- `0x1400067c4`
- `0x140006c88`
- `0x140006f7c`
- `0x14000708c`
- `0x1400072c0`
- `0x14000757c`
- `0x140007930`
- `0x140007c14`
- `0x140007f74`
- `0x1400085ac`
- `0x140008854`
- `0x140008994`
- `0x140008eb0`
- `0x14000919c`
- `0x140009888`
- `0x14000997c`
- `0x140009cf0`
- `0x14000a568`
- `0x14000b5d0`
- `0x14000b8c8`
- `0x14000bb38`
- `0x14000c740`
- `0x14000d298`
- `0x14000e790`
- `0x14000eedc`
- `0x14000f1b0`
- `0x14000f700`
- `0x140010330`
- `0x140010c38`
- `0x140010ed0`
- `0x1400111d0`
- `0x140011404`
- `0x140011e90`
- `0x1400144dc`
- `0x1400146ac`
- `0x140014958`
- `0x140014dd8`
- `0x140014eb0`
- `0x140015000`
- `0x140015254`
- `0x14001550c`
- `0x140015794`
- `0x140015910`

## callees

- `0x140001190`
- `0x1400175a0`

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
0x1400175a0  cmp     rcx, cs:__security_cookie
0x1400175a7  jnz     short loc_1400175B9
0x1400175a9  rol     rcx, 10h
0x1400175ad  test    cx, 0FFFFh
0x1400175b2  jnz     short loc_1400175B5
0x1400175b4  retn
0x1400175b5  ror     rcx, 10h
0x1400175b9  jmp     __report_gsfailure
```
