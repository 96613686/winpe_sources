# __security_check_cookie

- ea: `0x140003770`
- end: `0x14000378e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001700`
- `0x140001840`
- `0x1400019d4`
- `0x140002064`
- `0x1400020dc`
- `0x1400021d0`
- `0x1400028a4`
- `0x1400036a8`

## callees

- `0x140001010`
- `0x140003770`

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
0x140003770  cmp     rcx, cs:__security_cookie
0x140003777  jnz     short loc_140003789
0x140003779  rol     rcx, 10h
0x14000377d  test    cx, 0FFFFh
0x140003782  jnz     short loc_140003785
0x140003784  retn
0x140003785  ror     rcx, 10h
0x140003789  jmp     __report_gsfailure
```
