# __security_check_cookie

- ea: `0x14000d1f0`
- end: `0x14000d20e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010b0`
- `0x140002230`
- `0x140004958`
- `0x140004bf4`
- `0x1400054ac`
- `0x140005850`
- `0x140005dd0`
- `0x140006834`
- `0x140006bac`
- `0x1400077ec`
- `0x140007a6c`
- `0x140008338`
- `0x140009838`
- `0x14000a178`
- `0x14000a3b8`
- `0x14000a560`
- `0x14000a7a8`
- `0x14000aaa4`
- `0x14000b344`
- `0x14000b3a0`
- `0x14000b434`
- `0x14000b5d8`
- `0x14000b704`
- `0x14000b800`
- `0x14000c018`
- `0x14000c230`
- `0x14000c868`
- `0x14000ccd0`
- `0x14000d130`

## callees

- `0x140001b00`
- `0x14000d1f0`

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
0x14000d1f0  cmp     rcx, cs:__security_cookie
0x14000d1f7  jnz     short loc_14000D209
0x14000d1f9  rol     rcx, 10h
0x14000d1fd  test    cx, 0FFFFh
0x14000d202  jnz     short loc_14000D205
0x14000d204  retn
0x14000d205  ror     rcx, 10h
0x14000d209  jmp     __report_gsfailure
```
