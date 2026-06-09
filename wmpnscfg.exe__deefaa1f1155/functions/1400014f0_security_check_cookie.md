# __security_check_cookie

- ea: `0x1400014f0`
- end: `0x14000150e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400028bc`
- `0x140003924`
- `0x140003ccc`
- `0x140003e1c`
- `0x140003fac`
- `0x140004190`
- `0x1400049f8`
- `0x140004d0c`
- `0x140005034`
- `0x140006d7c`
- `0x140006fe8`
- `0x140007490`

## callees

- `0x1400014f0`
- `0x140001790`

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
0x1400014f0  cmp     rcx, cs:__security_cookie
0x1400014f7  jnz     short loc_140001509
0x1400014f9  rol     rcx, 10h
0x1400014fd  test    cx, 0FFFFh
0x140001502  jnz     short loc_140001505
0x140001504  retn
0x140001505  ror     rcx, 10h; StackCookie
0x140001509  jmp     __report_gsfailure
```
