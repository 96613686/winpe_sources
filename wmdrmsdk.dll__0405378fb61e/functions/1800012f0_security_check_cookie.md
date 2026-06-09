# __security_check_cookie

- ea: `0x1800012f0`
- end: `0x18000130e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001120`
- `0x1800012f0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie == _security_cookie )
  {
    v1 = __ROL8__(StackCookie, 16);
    if ( !(_WORD)v1 )
      return;
    StackCookie = __ROR8__(v1, 16);
  }
  sub_180001120(StackCookie);
}

```

## disassembly

```asm
0x1800012f0  cmp     rcx, cs:__security_cookie
0x1800012f7  jnz     short loc_180001309
0x1800012f9  rol     rcx, 10h
0x1800012fd  test    cx, 0FFFFh
0x180001302  jnz     short loc_180001305
0x180001304  retn
0x180001305  ror     rcx, 10h
0x180001309  jmp     sub_180001120
```
