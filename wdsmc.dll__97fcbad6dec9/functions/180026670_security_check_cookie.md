# __security_check_cookie

- ea: `0x180026670`
- end: `0x18002668e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `46`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800020bc`
- `0x180002368`
- `0x180002c70`
- `0x180003590`
- `0x180003c0c`
- `0x1800053a0`
- `0x1800067f0`
- `0x180007e64`
- `0x180008040`
- `0x1800082d0`
- `0x18000b560`
- `0x18000b8e8`
- `0x18000bb0c`
- `0x18000bdd4`
- `0x18000d454`
- `0x18000ea7c`
- `0x18000ec74`
- `0x18000f688`
- `0x18000fa3c`
- `0x1800148b4`
- `0x180015c34`
- `0x180015e94`
- `0x180016270`
- `0x180016340`
- `0x180016904`
- `0x180016e70`
- `0x180017c60`
- `0x180017dc0`
- `0x180018240`
- `0x18001853c`
- `0x180018770`
- `0x18001b9f8`
- `0x18001cac4`
- `0x18001e398`
- `0x18001ed10`
- `0x18001fe54`
- `0x180020840`
- `0x180020dc8`
- `0x180022674`
- `0x1800227d4`
- `0x180022d54`
- `0x180022f20`
- `0x1800237f0`
- `0x180023a78`
- `0x180023b60`
- `0x180026cac`

## callees

- `0x180026670`
- `0x1800269e0`

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
0x180026670  cmp     rcx, cs:__security_cookie
0x180026677  jnz     short ReportFailure
0x180026679  rol     rcx, 10h
0x18002667d  test    cx, 0FFFFh
0x180026682  jnz     short RestoreRcx
0x180026684  retn
0x180026685  ror     rcx, 10h
0x180026689  jmp     __report_gsfailure
```
