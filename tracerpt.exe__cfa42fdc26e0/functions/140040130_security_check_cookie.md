# __security_check_cookie

- ea: `0x140040130`
- end: `0x14004014e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `96`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400032c0`
- `0x140003a30`
- `0x14000556c`
- `0x140005914`
- `0x140005acc`
- `0x140006db8`
- `0x140007658`
- `0x1400078ec`
- `0x140007d94`
- `0x140008444`
- `0x140008b40`
- `0x140008d14`
- `0x140009258`
- `0x14000a0d4`
- `0x14000acc4`
- `0x14000b43c`
- `0x14000bfe4`
- `0x14000c964`
- `0x14000d174`
- `0x14000d4a8`
- `0x14000d598`
- `0x14000f6f0`
- `0x14000faa4`
- `0x14000fd88`
- `0x140010a88`
- `0x140011120`
- `0x140011f98`
- `0x14001232c`
- `0x1400130d0`
- `0x1400137b8`
- `0x140013c48`
- `0x1400144c4`
- `0x14001489c`
- `0x140014b98`
- `0x140015e84`
- `0x140016ae0`
- `0x14001717c`
- `0x1400172f4`
- `0x140017398`
- `0x140018d04`
- `0x1400192b4`
- `0x14001a3b0`
- `0x14001a760`
- `0x14001ab78`
- `0x14001c320`
- `0x14001e6d8`
- `0x14001f040`
- `0x14001f0f8`
- `0x14001f4ac`
- `0x140020310`

## callees

- `0x140002450`
- `0x140040130`

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
0x140040130  cmp     rcx, cs:__security_cookie
0x140040137  jnz     short loc_140040149
0x140040139  rol     rcx, 10h
0x14004013d  test    cx, 0FFFFh
0x140040142  jnz     short loc_140040145
0x140040144  retn
0x140040145  ror     rcx, 10h
0x140040149  jmp     __report_gsfailure
```
