# __security_check_cookie

- ea: `0x140007770`
- end: `0x14000778e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400028e0`
- `0x140003368`
- `0x140003610`
- `0x140003bd0`
- `0x140003f74`
- `0x140004424`
- `0x1400047c0`
- `0x1400058c0`
- `0x140005964`
- `0x140005d7c`
- `0x140005eb8`
- `0x14000697c`
- `0x1400074e0`
- `0x140007674`

## callees

- `0x140001ce0`
- `0x140007770`

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
0x140007770  cmp     rcx, cs:__security_cookie
0x140007777  jnz     short loc_140007789
0x140007779  rol     rcx, 10h
0x14000777d  test    cx, 0FFFFh
0x140007782  jnz     short loc_140007785
0x140007784  retn
0x140007785  ror     rcx, 10h
0x140007789  jmp     __report_gsfailure
```
