# __security_check_cookie

- ea: `0x1400015a0`
- end: `0x1400015be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400028d0`
- `0x140003444`
- `0x1400036e0`
- `0x140003b94`
- `0x140003ffc`
- `0x140004944`
- `0x140004d00`
- `0x14000535c`
- `0x1400064cc`
- `0x140006a7c`
- `0x140006c24`
- `0x140006e44`
- `0x14000737c`
- `0x140007b40`
- `0x140008010`
- `0x14000897c`
- `0x1400092c4`
- `0x140009540`
- `0x140009d94`
- `0x14000abe4`
- `0x14000ae24`
- `0x14000b100`

## callees

- `0x1400015a0`
- `0x140001b80`

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
0x1400015a0  cmp     rcx, cs:__security_cookie
0x1400015a7  jnz     short loc_1400015B9
0x1400015a9  rol     rcx, 10h
0x1400015ad  test    cx, 0FFFFh
0x1400015b2  jnz     short loc_1400015B5
0x1400015b4  retn
0x1400015b5  ror     rcx, 10h; StackCookie
0x1400015b9  jmp     __report_gsfailure
```
