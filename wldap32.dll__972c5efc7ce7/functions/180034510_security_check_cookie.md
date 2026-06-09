# __security_check_cookie

- ea: `0x180034510`
- end: `0x18003452e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010b4`
- `0x1800037a8`
- `0x180012ab0`
- `0x1800164a0`
- `0x180017854`
- `0x18001b0d4`
- `0x18001ba9c`
- `0x18001d470`
- `0x18001da40`
- `0x18001e8e0`
- `0x18001ef6c`
- `0x180020990`
- `0x180021454`
- `0x18002448c`
- `0x180024a60`
- `0x180024df0`
- `0x180026490`
- `0x1800277d8`
- `0x18002b284`
- `0x18002b904`
- `0x18002d67c`
- `0x18002e24c`
- `0x1800314a8`
- `0x18003266c`
- `0x180032bd8`
- `0x180035a58`
- `0x180035b50`
- `0x180036134`
- `0x1800362a8`
- `0x18003651c`
- `0x180036b94`
- `0x180036ec4`
- `0x180037ecc`
- `0x1800381e0`
- `0x180038f84`
- `0x1800398ec`
- `0x18003d78c`
- `0x18003de10`
- `0x18003df3c`
- `0x180042484`
- `0x18004294c`
- `0x1800429f4`
- `0x1800434f0`
- `0x1800491d4`
- `0x18004c308`
- `0x18004c618`

## callees

- `0x180034510`
- `0x180034aa0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180034510  cmp     rcx, cs:__security_cookie
0x180034517  jnz     short ReportFailure
0x180034519  rol     rcx, 10h
0x18003451d  test    cx, 0FFFFh
0x180034522  jnz     short RestoreRcx
0x180034524  retn
0x180034525  ror     rcx, 10h; StackCookie
0x180034529  jmp     __report_gsfailure
```
