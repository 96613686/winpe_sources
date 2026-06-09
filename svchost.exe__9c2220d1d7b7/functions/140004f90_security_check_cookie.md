# __security_check_cookie

- ea: `0x140004f90`
- end: `0x140004fae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001280`
- `0x1400014b0`
- `0x140001970`
- `0x1400023b0`
- `0x1400029e0`
- `0x140002e20`
- `0x1400030b0`
- `0x140003470`
- `0x140003cd0`
- `0x140004720`
- `0x140006520`
- `0x140006cbc`
- `0x140006d84`
- `0x140007500`
- `0x1400086f8`
- `0x140008c60`

## callees

- `0x140004f90`
- `0x140005510`

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
0x140004f90  cmp     rcx, cs:__security_cookie
0x140004f97  jnz     short loc_140004FA9
0x140004f99  rol     rcx, 10h
0x140004f9d  test    cx, 0FFFFh
0x140004fa2  jnz     short loc_140004FA5
0x140004fa4  retn
0x140004fa5  ror     rcx, 10h; StackCookie
0x140004fa9  jmp     __report_gsfailure
```
