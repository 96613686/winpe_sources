# __security_check_cookie

- ea: `0x140003cc0`
- end: `0x140003cde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001fe4`
- `0x140002118`
- `0x1400021c8`
- `0x1400022c4`
- `0x140002a40`
- `0x140003b4c`
- `0x140003c24`

## callees

- `0x140001360`
- `0x140003cc0`

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
0x140003cc0  cmp     rcx, cs:__security_cookie
0x140003cc7  jnz     short loc_140003CD9
0x140003cc9  rol     rcx, 10h
0x140003ccd  test    cx, 0FFFFh
0x140003cd2  jnz     short loc_140003CD5
0x140003cd4  retn
0x140003cd5  ror     rcx, 10h
0x140003cd9  jmp     __report_gsfailure
```
