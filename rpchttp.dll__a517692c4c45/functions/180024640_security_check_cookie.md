# __security_check_cookie

- ea: `0x180024640`
- end: `0x18002465e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `35`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005d50`
- `0x1800081e8`
- `0x18000c1a0`
- `0x18000cbdc`
- `0x18000d288`
- `0x18000d4fc`
- `0x18000d934`
- `0x18000dc80`
- `0x18000dfe8`
- `0x18000f74c`
- `0x180010d34`
- `0x180016ee4`
- `0x180019b1c`
- `0x18001cb10`
- `0x18001d1d8`
- `0x18001d2b8`
- `0x18001d380`
- `0x18001d450`
- `0x18001deb0`
- `0x18001e4a4`
- `0x18001e524`
- `0x18001e5bc`
- `0x18001e670`
- `0x18001e718`
- `0x18001e7b4`
- `0x18001fc58`
- `0x1800208cc`
- `0x180020b64`
- `0x18002305c`
- `0x180023428`
- `0x180023ff4`
- `0x1800242e8`
- `0x180024368`
- `0x180024408`
- `0x18002452c`

## callees

- `0x1800010e0`
- `0x180024640`

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
0x180024640  cmp     rcx, cs:__security_cookie
0x180024647  jnz     short loc_180024659
0x180024649  rol     rcx, 10h
0x18002464d  test    cx, 0FFFFh
0x180024652  jnz     short loc_180024655
0x180024654  retn
0x180024655  ror     rcx, 10h
0x180024659  jmp     __report_gsfailure
```
